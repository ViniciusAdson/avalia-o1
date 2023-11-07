# avalia-o1
RESOLUÇÕES DA SEGUNDA LISTA AVALIATIVA:

QUESTÃO 1:

#include <stdio.h>

int main() {
    int valores[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int tamanhoAtual = 10;

    while (tamanhoAtual > 1) {
        
        printf("Conjunto atual: ");
        for (int i = 0; i < tamanhoAtual; i++) {
            printf("%d ", valores[i]);
        }
        printf("\n");

        
        int novoTamanho = (tamanhoAtual % 2 == 0) ? tamanhoAtual / 2 : (tamanhoAtual / 2) + 1;
        int novoConjunto[novoTamanho];

        
        for (int i = 0, j = 0; i < tamanhoAtual - 1; i += 2, j++) {
            novoConjunto[j] = valores[i] + valores[i + 1];
        }

        
        for (int i = 0; i < novoTamanho; i++) {
            valores[i] = novoConjunto[i];
        }

        tamanhoAtual = novoTamanho;
    }

    printf("\nResultado final: %d\n", valores[0]);

    return 0;
}




QUESTÃO 2:


#include <stdio.h>
#include <stdlib.h>


int main(int argc, char *argv[]) {


    char time1[50], time2[50];
    float G1, G2, L1, L2, Z1, Z2, V1, V2, M1, M2, A1, A2;
    float F1, F2;

    printf("Digite o nome do Time 1: ");
    scanf("%s", time1);

    printf("Digite a força do goleiro do Time 1: ");
    scanf("%f", &G1);
    printf("Digite a força dos laterais do Time 1: ");
    scanf("%f", &L1);
    printf("Digite a força dos zagueiros do Time 1: ");
    scanf("%f", &Z1);
    printf("Digite a força dos volantes do Time 1: ");
    scanf("%f", &V1);
    printf("Digite a força dos meias do Time 1: ");
    scanf("%f", &M1);
    printf("Digite a força dos atacantes do Time 1: ");
    scanf("%f", &A1);

    printf("Digite o nome do Time 2: ");
    scanf("%s", time2);

    printf("Digite a força do goleiro do Time 2: ");
    scanf("%f", &G2);
    printf("Digite a força dos laterais do Time 2: ");
    scanf("%f", &L2);
    printf("Digite a força dos zagueiros do Time 2: ");
    scanf("%f", &Z2);
    printf("Digite a força dos volantes do Time 2: ");
    scanf("%f", &V2);
    printf("Digite a força dos meias do Time 2: ");
    scanf("%f", &M2);
    printf("Digite a força dos atacantes do Time 2: ");
    scanf("%f", &A2);

    F1 = (8 * G1 + 10 * (L1 + L2) + 5 * (Z1 + Z2) + 8 * (V1 + V2) + 11 * (M1 + M2) + 12 * (A1 + A2)) / 100;
    F2 = (8 * G2 + 10 * (L1 + L2) + 5 * (Z1 + Z2) + 8 * (V1 + V2) + 11 * (M1 + M2) + 12 * (A1 + A2)) / 100;

    if (F1 > F2) {
        printf("%s é o time mais forte!\n", time1);
    } else if (F2 > F1) {
        printf("%s é o time mais forte!\n", time2);
    } else {
        printf("Os times têm a mesma força!\n");
    }

    return 0;
}

QUESTÃO 3:


#include <stdio.h>
#include <string.h>


int main(){
    int matrizA[4][4];
    int matrizB[4][4];
    int resultado[4][4];
    char operacao[5];
    
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matrizA[i][j]);
      }
    }
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matrizB[i][j]);
      }
    }

    scanf("%s", operacao);

    if (strcmp(operacao,"soma")==0)
    {
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j] = matrizA[i][j] + matrizB[i][j];
            }
        }
     }
    else if (strcmp(operacao,"sub")==0)
    {
       for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j] = matrizA[i][j] - matrizB[i][j];
            }
       }
    }
    else if (strcmp(operacao,"mult")==0)
    {
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j]=0;
                
                for (int k = 0; k < 4; k++) {
                  resultado[i][j] += matrizA[i][k] * matrizB[k][j];
                 }
            }
        }
    }
    
    
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         printf("%*d",+4,resultado[i][j]);
      }
      printf("\n");
    }
    return 0;
}
