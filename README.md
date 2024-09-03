#include <stdio.h>

#define DIAS_NO_MES 30

void calcular_comida(float quantidade, float comida_por_dia, float preco_por_kilo, float* comida_diaria, float* comida_mensal, float* custo_diario, float* custo_mensal) {
    *comida_diaria = quantidade * comida_por_dia;
    *comida_mensal = *comida_diaria * DIAS_NO_MES;
    *custo_diario = *comida_diaria * preco_por_kilo;
    *custo_mensal = *comida_mensal * preco_por_kilo;
}

int main() {
    int num_animais;
    printf("Digite o número de tipos de animais: ");
    scanf("%d", &num_animais);

    for (int i = 0; i < num_animais; i++) {
        char tipo_animal[50];
        float quantidade, comida_por_dia, preco_por_kilo;
        float comida_diaria, comida_mensal, custo_diario, custo_mensal;

        printf("\nDigite o tipo de animal %d: ", i + 1);
        scanf(" %49[^\n]", tipo_animal);

        printf("Digite a quantidade de %s: ", tipo_animal);
        scanf("%f", &quantidade);

        printf("Digite a quantidade de comida (em kg) que cada %s consome por dia: ", tipo_animal);
        scanf("%f", &comida_por_dia);

        printf("Digite o preço por quilo da comida para %s: ", tipo_animal);
        scanf("%f", &preco_por_kilo);

        calcular_comida(quantidade, comida_por_dia, preco_por_kilo, &comida_diaria, &comida_mensal, &custo_diario, &custo_mensal);

        printf("\nResumo para %s:\n", tipo_animal);
        printf("Quantidade total de comida necessária por dia: %.2f kg\n", comida_diaria);
        printf("Quantidade total de comida necessária por mês: %.2f kg\n", comida_mensal);
        printf("Custo diário: R$ %.2f\n", custo_diario);
        printf("Custo mensal: R$ %.2f\n", custo_mensal);
    }

    return 0;
}
