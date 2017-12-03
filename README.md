# TrabalhoForcaAV2Unilasalle
// Samuel Vítor da Rocha Silva Almeida

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int menu = 0;
char db[5][10] = {
  "bar",
  "carro",
  "filha",
  "cerveja",
  "biblia"
};

char ldig;
int letra = 0;
int palavra = 0;
int chanc = 6;
int tam = 0;

int inicio (void);
int jogo(void);
int forca (void);

int forca(){

    if(chanc == 5){
    printf("\n|____   \n");
	printf(" |O    \n");
	printf(" | \n");
	printf(" | \n");
    }

    if(chanc == 4){
    printf("\n|____   \n");
	printf(" | O    \n");
	printf(" |/ \n");
	printf(" | \n");
    }

    if(chanc == 3){
    printf("\n|____   \n");
	printf(" | O   \n");
	printf(" |/\\ \n");
	printf(" | \n");
    }
    if(chanc == 2){
    printf("\n|____   \n");
	printf(" | O   \n");
	printf(" |/\\ \n");
	printf(" |/ \n");
    }
    if(chanc == 1){
    printf("\n|____   \n");
	printf(" | O   \n");
	printf(" |/\\ \n");
	printf(" |/\\ \n");
    }
    if(chanc == 0){
    printf("\n|____   \n");
	printf(" | O   \n");
	printf(" |/\\ \n");
	printf(" |/\\ \n");
	printf(" \nF O R C A\n");
    }
}
  int inicio() {
    tam = strlen(&db[palavra]);
        if (letra == tam) {
          	printf("\nPARABENS VOCE ACERTOU!!!!!\n\n");
          	printf("\n[SISTEMA] GERANDO NOVA PALAVRA \n");
          	letra = 0;
          	ldig = "0";
          	chanc = 6;
          	jogo();
            }
           if(chanc == 0){
          	printf("\n[SISTEMA] VOCE PERDEU, JOGUE NOVAMENTE!!\n");
            exit(0);
          }
          if(chanc > 0){
            printf("\nDigite uma letra para a %d letra da palavra - \n ",letra+1);
            scanf(" %c", &ldig);
            if (ldig == db[palavra][letra]) {
              printf("\nCerta resposta!");
              letra++;
              inicio();
            } else {
              chanc--;
              printf("\nVoce errou! Ainda tem %d chances", chanc);
              forca();
              inicio();}
    }

}

int jogo(){

	  srand(time(NULL));
    	  palavra = rand() % 5;
    	  tam = strlen(&db[palavra]);

          if (palavra == 0) {
       	    printf("\n|____   \n");
            printf(" |    \n");
            printf(" | \n");
            printf(" | \n");
          } else if (palavra == 1) {
            printf("\n|____   \n");
            printf(" |    \n");
            printf(" | \n");
            printf(" | \n");
          } else if (palavra == 2) {
            printf("\n|____   \n");
            printf(" |    \n");
            printf(" | \n");
            printf(" | \n");
          } else if (palavra == 3) {
            printf("\n|____   \n");
            printf(" |    \n");
            printf(" | \n");
            printf(" | \n");
          } else if (palavra == 4) {
            printf("\n|____   \n");
            printf(" |    \n");
            printf(" | \n");
            printf(" | \n");
          }
inicio();
}

int main(){
	jogo();
	return 0;
}
