#include <stdio.h>

#define SIZE 9

int main(void) {
    int instancia, x;

    printf("Digite a quantidade de jogos: ");
    scanf("%d", &instancia);

    for (x = 0; x < instancia; x++) {
        int sudoku[SIZE][SIZE];
        int teste = 1; // Inicialize teste como verdadeiro

        // Entrada do jogo Sudoku
        printf("Digite o jogo Sudoku #%d:\n", x + 1);
        for (int i = 0; i < SIZE; i++) {
            for (int j = 0; j < SIZE; j++) {
                scanf("%d", &sudoku[i][j]);
            }
        }

        // Verificar linhas e colunas
        for (int i = 0; i < SIZE; i++) {
            for (int j = 0; j < SIZE; j++) {
                for (int z = i + 1; z < SIZE; z++) {
                    // Verificar linhas
                    if (sudoku[i][j] == sudoku[z][j])
                        teste = 0;
                    // Verificar colunas
                    if (sudoku[j][i] == sudoku[j][z])
                        teste = 0;
                }
            }
        }

        // Verificar submatrizes
        for (int i = 0; i < SIZE; i += 3) {
            for (int j = 0; j < SIZE; j += 3) {
                int freq[SIZE + 1] = {0}; 
        // Inicializar contador de frequência

                for (int k = i; k < i + 3; k++) {
                    for (int l = j; l < j + 3; l++) {
                        freq[sudoku[k][l]]++;
                    }
                }

                for (int num = 1; num <= SIZE; num++) {
                    if (freq[num] != 1)
                        teste = 0;
                }
            }
        }

        // Exibir resultado para este jogo Sudoku
        if (teste == 1)
            printf("Jogo Sudoku #%d: SIM\n", x + 1);
        else
            printf("Jogo Sudoku #%d: NÃO\n", x + 1);
    }

    return 0;
}

