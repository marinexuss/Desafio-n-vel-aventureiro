#include <stdio.h>
#include <string.h>
#include <ctype.h>

// Definição da estrutura da carta
typedef struct {
    char pais[50];
    char codigo[10];
    int populacao;
    float area;
    float pib;
    int pontos_turisticos;
    float densidade;
} Carta;

// Função para calcular a densidade demográfica
void calcular_densidade(Carta *carta) {
    if (carta->area > 0) {
        carta->densidade = carta->populacao / carta->area;
    } else {
        carta->densidade = 0;
    }
}

// Função para exibir os dados de uma carta
void exibir_carta(Carta carta) {
    printf("\nPaís: %s\n", carta.pais);
    printf("Código: %s\n", carta.codigo);
    printf("População: %d habitantes\n", carta.populacao);
    printf("Área: %.2f km²\n", carta.area);
    printf("PIB: %.2f milhões de USD\n", carta.pib);
    printf("Pontos turísticos: %d\n", carta.pontos_turisticos);
    printf("Densidade demográfica: %.2f hab/km²\n", carta.densidade);
}

// Função para exibir o menu e obter a escolha do usuário
int exibir_menu() {
    int escolha;
    
    printf("\n=== MENU SUPER TRUNFO ===\n");
    printf("Escolha o atributo para comparar:\n");
    printf("1. População\n");
    printf("2. Área\n");
    printf("3. PIB\n");
    printf("4. Pontos turísticos\n");
    printf("5. Densidade demográfica\n");
    printf("0. Sair\n");
    printf("Digite sua escolha: ");
    
    scanf("%d", &escolha);
    
    return escolha;
}

// Função para comparar duas cartas
void comparar_cartas(Carta c1, Carta c2, int atributo) {
    printf("\n=== RESULTADO DA COMPARAÇÃO ===\n");
    printf("País 1: %s\n", c1.pais);
    printf("País 2: %s\n", c2.pais);
    
    switch(atributo) {
        case 1: // População
            printf("Atributo: População\n");
            printf("%s: %d habitantes\n", c1.pais, c1.populacao);
            printf("%s: %d habitantes\n", c2.pais, c2.populacao);
            
            if (c1.populacao > c2.populacao) {
                printf("Vencedor: %s\n", c1.pais);
            } else if (c2.populacao > c1.populacao) {
                printf("Vencedor: %s\n", c2.pais);
            } else {
                printf("Empate!\n");
            }
            break;
            
        case 2: // Área
            printf("Atributo: Área\n");
            printf("%s: %.2f km²\n", c1.pais, c1.area);
            printf("%s: %.2f km²\n", c2.pais, c2.area);
            
            if (c1.area > c2.area) {
                printf("Vencedor: %s\n", c1.pais);
            } else if (c2.area > c1.area) {
                printf("Vencedor: %s\n", c2.pais);
            } else {
                printf("Empate!\n");
            }
            break;
            
        case 3: // PIB
            printf("Atributo: PIB\n");
            printf("%s: %.2f milhões de USD\n", c1.pais, c1.pib);
            printf("%s: %.2f milhões de USD\n", c2.pais, c2.pib);
            
            if (c1.pib > c2.pib) {
                printf("Vencedor: %s\n", c1.pais);
            } else if (c2.pib > c1.pib) {
                printf("Vencedor: %s\n", c2.pais);
            } else {
                printf("Empate!\n");
            }
            break;
            
        case 4: // Pontos turísticos
            printf("Atributo: Pontos turísticos\n");
            printf("%s: %d pontos\n", c1.pais, c1.pontos_turisticos);
            printf("%s: %d pontos\n", c2.pais, c2.pontos_turisticos);
            
            if (c1.pontos_turisticos > c2.pontos_turisticos) {
                printf("Vencedor: %s\n", c1.pais);
            } else if (c2.pontos_turisticos > c1.pontos_turisticos) {
                printf("Vencedor: %s\n", c2.pais);
            } else {
                printf("Empate!\n");
            }
            break;
            
        case 5: // Densidade demográfica
            printf("Atributo: Densidade demográfica\n");
            printf("%s: %.2f hab/km²\n", c1.pais, c1.densidade);
            printf("%s: %.2f hab/km²\n", c2.pais, c2.densidade);
            
            // Regra invertida para densidade (menor valor vence)
            if (c1.densidade < c2.densidade) {
                printf("Vencedor: %s\n", c1.pais);
            } else if (c2.densidade < c1.densidade) {
                printf("Vencedor: %s\n", c2.pais);
            } else {
                printf("Empate!\n");
            }
            break;
            
        default:
            printf("Atributo inválido!\n");
    }
}

int main() {
    // Criando duas cartas de exemplo
    Carta carta1 = {
        .pais = "Brasil",
        .codigo = "BR001",
        .populacao = 213000000,
        .area = 8515767.049,
        .pib = 1847000.00,
        .pontos_turisticos = 25
    };
    
    Carta carta2 = {
        .pais = "Argentina",
        .codigo = "AR001",
        .populacao = 45380000,
        .area = 2780400.00,
        .pib = 445500.00,
        .pontos_turisticos = 18
    };
    
    // Calculando densidade para ambas as cartas
    calcular_densidade(&carta1);
    calcular_densidade(&carta2);
    
    // Exibindo informações das cartas
    printf("=== CARTAS DISPONÍVEIS ===\n");
    exibir_carta(carta1);
    exibir_carta(carta2);
    
    // Loop principal do jogo
    int opcao;
    do {
        opcao = exibir_menu();
        
        switch(opcao) {
            case 1:
            case 2:
            case 3:
            case 4:
            case 5:
                comparar_cartas(carta1, carta2, opcao);
                break;
                
            case 0:
                printf("Saindo do jogo...\n");
                break;
                
            default:
                printf("Opção inválida! Tente novamente.\n");
        }
        
        if (opcao != 0) {
            printf("\nPressione Enter para continuar...");
            while (getchar() != '\n'); // Limpa o buffer
            getchar(); // Espera Enter
        }
        
    } while (opcao != 0);
    
    return 0;
}
