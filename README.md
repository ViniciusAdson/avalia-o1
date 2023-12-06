Lista avaliativa 2

Questão 1

#include <stdio.h>

int main(){
    int n = 10;
    int valores[10];
    int conjunton[10];
    for (int i = 0; i < n; i++) {
        scanf("%d", &valores[i]);
    }
    while (n > 1)
    {
         for (int i = 0; i < n; i++) {
            printf("%d", valores[i]);
            
            if (i < n - 1) {
                printf(" ");
             }
         }
         printf("\n");
         for (int i = 0; i < n - 1; i++)
         {
            conjunton[i] = valores[i] + valores[i+1];
         }
         n--;
         for (int i = 0; i < n; i++)
         {
            valores[i] = conjunton[i];
         }
         
    }
    printf("%d\n", valores[0]);
    


    return 0;
}

Questão 2
#include <stdio.h>

float calculaForcaPonderada(int forcas[]) {
    return (8 * forcas[0] + 10 * (forcas[1] + forcas[2]) + 5 * (forcas[3] + forcas[4]) + 8 * (forcas[5] + forcas[6]) + 11 * (forcas[7] + forcas[8]) + 12 * (forcas[9] + forcas[10])) / 100.0;
}

int main() {
    int forcasA[11] = {0}, forcasTimeB[11] = {0};
    char nomeA[31], nomeTimeB[31];
    char nomeJogador[31], posicaoJogador;
    int forcaJogador;
    
    
    scanf(" %30[^\n]", nomeA);
    for (int i = 0; i < 11; i++) {
        scanf(" %30[^;]; %c; %d", nomeJogador, &posicaoJogador, &forcaJogador);

        int posicao = (posicaoJogador == 'L') ? (forcasTimeA[1] == 0) ? 1 : 2 : 
        (posicaoJogador == 'Z') ? (forcasA[3] == 0) ? 3 : 4 : 
        (posicaoJogador == 'V') ? (forcasA[5] == 0) ? 5 : 6 : 
        (posicaoJogador == 'M') ? (forcasA[7] == 0) ? 7 : 8 : 
        (posicaoJogador == 'A') ? (forcasA[9] == 0) ? 9 : 10 : 0;

        if (forcasA[posicao] == 0)
            forcasA[posicao] = forcaJogador;
    }

    scanf(" %30[^\n]", nomeTimeB);
    for (int i = 0; i < 11; i++) {
        scanf(" %30[^;]; %c; %d", nomeJogador, &posicaoJogador, &forcaJogador);

        int posicao = (posicaoJogador == 'L') ? (forcasTimeB[1] == 0) ? 1 : 2 : 
        (posicaoJogador == 'Z') ? (forcasB[3] == 0) ? 3 : 4 : 
        (posicaoJogador == 'V') ? (forcasB[5] == 0) ? 5 : 6 : 
        (posicaoJogador == 'M') ? (forcasB[7] == 0) ? 7 : 8 :     (posicaoJogador == 'A') ? (forcasB[9] == 0) ? 9 : 10 : 0;

        if (forcasB[posicao] == 0)
            forcasB[posicao] = forcaJogador;
    }

    float forcaA = calculaForcaPonderada(forcasA);
    float forcaB = calculaForcaPonderada(forcasB);

    printf("%s: %.2f de forca\n%s: %.2f de forca\n", nomeTimeA, forcaA, nomeB, forcaB);

    if (forcaA > forcaB)
        printf("%s eh mais forte\n", nomeA);
    else if (forcaB > forcaA)
        printf("%s eh mais forte\n", nomeB);
    else
        printf("Os times têm a mesma forca\n");

    return 0;
}

QUESTÃO 3

#include <stdio.h>
#include <string.h>


int main(){
    int matriz1[4][4];
    int matriz1[4][4];
    int resultado[4][4];
    char valor[5];
    
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matriz1[i][j]);
      }
    }
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matrizB[i][j]);
      }
    }

    scanf("%s", );

    if (strcmp(valor,"soma")==0)
    {
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j] = matriz1[i][j] + matriz2[i][j];
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
