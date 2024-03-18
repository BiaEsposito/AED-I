#include <stdio.h>

int main(void){
    int inst, x, i, j, linha, coluna;
    scanf("%d", &inst);
    
    for(x = 0; x < inst; x++){
        int sudoku[9][9], teste = 0;
        
        // Receber o jogo
        for(i = 0; i < 9; i++){
            for(j = 0; j < 9; j++){
                scanf("%d", &sudoku[i][j]);
            }
        }
        
        // Verificar linhas e colunas
        for(i = 0; i < 9; i++){
            for(j = 0; j < 9; j++){
                for(int z = j + 1; z < 9; z++){
                    if(sudoku[i][j] == sudoku[i][z])
                        teste = 1;
                }
                for(int z = i + 1; z < 9; z++){
                    if(sudoku[i][j] == sudoku[z][j])
                        teste = 1;
                }
                if(sudoku[i][j] < 1 || sudoku[i][j] > 9)
                    teste = 1;
            }
        }

        // Verificar regiões 3x3
        for(linha = 0; linha < 3; linha++){
            for(coluna = 0; coluna < 3; coluna++){
                int parte[9] = {0};
                for(i = linha * 3; i < linha * 3 + 3; i++){
                    for(j = coluna * 3; j < coluna * 3 + 3; j++ ){
                        int num = sudoku[i][j];
                        if(parte[num - 1] != 0){
                            teste = 1;
                        }
                        parte[num - 1] = 1;
                    }
                }
            }
        }
        
        // Mostrar instâncias
        printf("INSTANCIA %d\n", x + 1);
        if(teste == 0){
            printf("SIM\n\n");
        } else {
            printf("NAO\n\n");
        }
    }
    
    return 0;
}

