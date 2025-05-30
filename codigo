#include <stdio.h>

#define TAM_TABULEIRO 10
#define TAM_NAVIO 3

// Função para verificar se um navio pode ser posicionado sem sair do tabuleiro
int pode_posicionar(int tabuleiro[10][10], int linha, int coluna, int orientacao) {
    for (int i = 0; i < TAM_NAVIO; i++) {
        if (orientacao == 0) { // Horizontal
            if (coluna + i >= TAM_TABULEIRO || tabuleiro[linha][coluna + i] != 0)
                return 0; // Fora dos limites ou já ocupado
        } else { // Vertical
            if (linha + i >= TAM_TABULEIRO || tabuleiro[linha + i][coluna] != 0)
                return 0;
        }
    }
    return 1; // Pode posicionar
}

// Função para posicionar o navio na matriz
void posicionar_navio(int tabuleiro[10][10], int linha, int coluna, int orientacao) {
    for (int i = 0; i < TAM_NAVIO; i++) {
        if (orientacao == 0) { // Horizontal
            tabuleiro[linha][coluna + i] = 3;
        } else { // Vertical
            tabuleiro[linha + i][coluna] = 3;
        }
    }
}

// Função para imprimir o tabuleiro
void exibir_tabuleiro(int tabuleiro[10][10]) {
    printf("Tabuleiro:\n");
    for (int i = 0; i < TAM_TABULEIRO; i++) {
        for (int j = 0; j < TAM_TABULEIRO; j++) {
            printf("%d ", tabuleiro[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int tabuleiro[TAM_TABULEIRO][TAM_TABULEIRO] = {0}; // Inicializa com 0 (água)

    // Coordenadas iniciais dos navios
    int linha_horizontal = 2, coluna_horizontal = 4;
    int linha_vertical = 5, coluna_vertical = 7;

    // Validação e posicionamento do navio horizontal
    if (pode_posicionar(tabuleiro, linha_horizontal, coluna_horizontal, 0)) {
        posicionar_navio(tabuleiro, linha_horizontal, coluna_horizontal, 0);
    } else {
        printf("Erro ao posicionar navio horizontal!\n");
        return 1;
    }

    // Validação e posicionamento do navio vertical
    if (pode_posicionar(tabuleiro, linha_vertical, coluna_vertical, 1)) {
        posicionar_navio(tabuleiro, linha_vertical, coluna_vertical, 1);
    } else {
        printf("Erro ao posicionar navio vertical!\n");
        return 1;
    }

    // Exibe o tabuleiro final
    exibir_tabuleiro(tabuleiro);

    return 0;
}
