#include <stdio.h>

int main(void){
    int sudoku[9][9], x,y,z, i, j, linha, coluna, inst;
    scanf("%d", &inst);
    int teste[inst];
    
    for(x=0; x<inst; x++){
        
        //receber o jogo
        for(i=0; i<9; i++){
            for(j=0; j<9;j++){
                scanf("%d", &sudoku[i][j]);
            }
        }
    }
    
    // comparar linha e coluna
    for(i=0; i<9; i++){
        for(j=0;j<9;j++){
            for(z=j+1; z<9; z++){
                if(sudoku[i][j] == sudoku[i][z])
                    teste[x]=1;
            for(z=i+1; z<0;z++){
                if(sudoku[i][j] == sudoku[z][j])
                    teste[x]=1;
                    
                if(sudoku[i][j]<1 || sudoku[i][j]>9)
                    teste[x]=1;
            }
            }
        }
    }
    
    for(linha=0; linha<3; linha++){
        for(coluna=0; coluna<3; coluna++){
            int parte[9] = {0};
            for(i= linha * 3; i < linha *3 +3; i++){
                for(j= coluna * 3; j < coluna * 3 + 3 ){
                    int num = sudoku[i][j];
                    if(parte[nu, - 1] != 0){
                        teste[x]=1;
                    }
                    parte[num - 1] = 1;
                }
            }
        }
    }
    
    // mostrar instancias 
    
    for(x=0; x< inst; x++){
        printf("instancia %d\n", x+1);
        switch(teste[x]){
            case 0:
                printf("NAO\n\n");
                break;
            case 1: 
                printf("NAO\n\n");
                break;
            default:
                printf("ERRO \n\n");
                break;
        
        }
    }
}

