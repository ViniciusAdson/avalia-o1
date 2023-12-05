#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct Music {
    char title[50];
    int favorite;
} Music;

void addMusic(Music *music, int index);
void listMusic(Music *music, int total);
void removeMusic(Music *music, int index, int total);

int main() {
    Music music[50];
    int total = 0;
    int option;

    do {
        printf("\nMenu de Musicas:\n");
        printf("1. Adicionar musica\n");
        printf("2. Listar musicas\n");
        printf("3. Remover musica\n");
        printf("4. Sair\n");
        printf("Digite sua opcao: ");
        scanf("%d", &option);

        switch (option) {
            case 1:
                addMusic(music, total);
                total++;
                break;
            case 2:
                listMusic(music, total);
                break;
            case 3:
                removeMusic(music, total - 1, total);
                total--;
                break;
            case 4:
                printf("Saindo...\n");
                break;
            default:
                printf("Opcao invalida! Tente novamente.\n");
        }
    } while (option != 4);

    return 0;
}

void addMusic(Music *music, int index) {
    printf("\nAdicionar musica:\n");
    printf("Digite o titulo da musica: ");
    fflush(stdin);
    gets(music[index].title);
    printf("Escolha a favorita:\n1. Sim\n2. Nao\n");
    scanf("%d", &music[index].favorite);
}

void listMusic(Music *music, int total) {
    int i;

    printf("\nLista de musicas:\n");
    for (i = 0; i < total; i++) {
        printf("%d. %s ", i + 1, music[i].title);
        if (music[i].favorite == 1) {
            printf("(Favorita)");
        }
        printf("\n");
    }
}

void removeMusic(Music *music, int index, int total) {
    int i;

    printf("\nRemover musica:\n");
    printf("Digite o numero da musica: ");
    scanf("%d", &index);

    if (index <= 0 || index > total) {
        printf("Musica invalida! Tente novamente.\n");
        return;
    }

    for (i = index - 1; i < total - 1; i++) {
        strcpy(music[i].title, music[i + 1].title);
        music[i].favorite = music[i + 1].favorite;
    }

    total--;
    printf("Musica removida com sucesso!\n");
}


