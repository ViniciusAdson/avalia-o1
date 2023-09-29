# avalia-o1
RESOLUÇÕES DA PRIMEIRA LISTA AVALIATIVA:

QUESTÃO 1:

#include <stdio.h>

int main() {
    int ano;

   
    printf("Digite um ano para verificar se ocorreram Jogos Olimpicos de Verao ou Copa do Mundo: ");
    scanf("%d", &ano);

    
    if (ano == 1930 || ano == 1934 || ano == 1938 || ano == 1950 || ano == 1954 || ano == 1958 || ano == 1962 || ano == 1966 ||  ano == 2018 || ano == 2022 || ano == 2026) {
        printf("A Copa do Mundo ocorreu em %d.\n", ano);
    } else {
        printf("A Copa do Mundo nao ocorreu em %d.\n", ano);
    }

    // Verifica se o ano corresponde a uma edição dos Jogos Olímpicos de Verão
    if (ano == 1896 || ano == 1900 || ano == 1904 || ano == 1908 || ano == 1912 || ano == 2012 || ano == 2016 || ano == 2020 || ano == 2024) {
        printf("Os Jogos Olimpicos de Verao ocorreram em %d.\n", ano);
    } else {
        printf("Os Jogos Olimpicos de Verao nao ocorreram em %d.\n", ano);
    }

    return 0;
}


QUESTÃO 2:


#include <stdio.h>
#include <stdlib.h>



int main(int argc, char *argv[]) {

    int numero, digito, soma = 0;
    
    printf("Digite um número inteiro: ");
    scanf("%d", &numero);
    

    if (numero % 2 == 0) {
        printf("O número é par.\n");
    } else {
        printf("O número é ímpar.\n");
    }
    
   
    while (numero != 0) {
        digito = numero % 10;
        soma += digito;
        numero /= 10;
    }
    
    printf("A soma dos dígitos do número é: %d\n", soma);
    
    return 0;
}

QUESTÃO 3:


#include <stdio.h>

int main() {
    int senha_cadastrada;
    int senha_digitada;

    // Cadastro da senha
    printf("Digite a senha a ser cadastrada (numero): ");
    scanf("%d", &senha_cadastrada);
    printf("Senha cadastrada com sucesso!\n");

    // Validação da senha
    printf("Digite a senha para validacao: ");
    scanf("%d", &senha_digitada);

    if (senha_digitada == senha_cadastrada) {
        printf("Senha correta! Acesso permitido.\n");
    } else {
        printf("Senha incorreta! Acesso negado.\n");
    }

    return 0;
}

QUESTÃO 4:

#include <stdio.h>

int main() {
    char nivel;
    double salario, aumento;

    printf("Digite o nivel do funcionario (a, b ou c): ");
    scanf(" %c", &nivel);  

    printf("Digite o salario do funcionario: ");
    scanf("%lf", &salario);

    switch (nivel) {
        case 'a':
            aumento = salario * 0.05;
            break;
        case 'b':
            aumento = salario * 0.07;
            break;
        case 'c':
            aumento = salario * 0.08;
            break;
        default:
            printf("Nivel de experiencia invalido.\n");
            return 1; 
    }

    double novo_salario = salario + aumento;
    printf("O novo salario do funcionario e: R$ %.2lf\n", novo_salario);

    return 0; 
}

QUESTÃO 5:

#include <stdio.h>

int main() {
    int num1, num2;

   
    printf("Digite o primeiro valor inteiro: ");
    scanf("%d", &num1);

    printf("Digite o segundo valor inteiro: ");
    scanf("%d", &num2);

    if (num1 > num2) {
        if (num1 % num2 == 0) {
            printf("%d e maior que %d e e multiplo de %d.\n", num1, num2, num2);
        } else {
            printf("%d e maior que %d, mas nao e multiplo de %d.\n", num1, num2, num2);
        }
    } else if (num2 > num1) {
        if (num2 % num1 == 0) {
            printf("%d e maior que %d e é multiplo de %d.\n", num2, num1, num1);
        } else {
            printf("%d e maior que %d, mas nao e multiplo de %d.\n", num2, num1, num1);
        }
    } else {
        printf("Os dois valores sao iguais.\n");
    }

    return 0;
}
