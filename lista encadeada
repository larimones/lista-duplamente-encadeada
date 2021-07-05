//MATRICULA - 2011100034	
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
  int dia;
  int mes;
  int ano;
} Data;

struct ficha_aluno {
  char matri [10];
  float media;
  char name[40];
  Data nasc;
  struct ficha_aluno  *prev, *next;
};
typedef struct ficha_aluno aluno;

//lista inversa
void listainversa(aluno *node){
  
    if(node != NULL){
        listainversa(node->next);
        printf("%s,",node->matri);
        printf("%s,",node->name);
        printf("%d/%d/%d,",node->nasc.dia, node->nasc.mes, node->nasc.ano);
        printf("%.2f\n", node->media);
    }
}
void printaralu(aluno *al)
{
  if (al== NULL){
    printf("Lista Vazia!\n");
    return;
  }
  aluno * text;
  for (text=al;text!=NULL;text=text->next)
  { 
    printf("%s,",text->matri);
    printf("%s,",text->name);
    printf("%d/%d/%d,",text->nasc.dia, text->nasc.mes, text->nasc.ano);
    printf("%.2f\n", text->media);

  }
}

aluno *getLast(aluno *al)
{
  aluno *text;
  for (text=al;text->next!=NULL;text=text->next);
  return text;
}
aluno *newaluno(aluno *alu)
{
  aluno *al, *text;
 
  al=(aluno *)malloc(sizeof(aluno));
  scanf("%s", al->matri);
  scanf("%s", al->name); 
  scanf("%d/%d/%d",&al->nasc.dia, &al->nasc.mes, &al->nasc.ano);
  scanf("%f", &al->media);
  al->next=NULL;
  if (alu==NULL)
  {
    return al;
  }
  text=getLast(alu);
  text->next=al;
  return alu;
}
aluno *excluialuno(aluno *first, char excluiMatri[10]){
    aluno *text, *ant = NULL;

    for(text = first; text != NULL; text=text->next){
        if (strcmp(text->matri,excluiMatri)==0){
            if (first == text){
                first = text->next;
            }else{
                ant->next = text->next;
            }
            free(text);
        }
        ant = text;
    }
    return first;
}

int main() {
  aluno * first = NULL, *text = NULL;
  // nao sei se ta crt
  
  int option =10;
  int cont =0;
  char matriexclui[10];
  while (option != 7) 
  {
    scanf("%d", &option);
    if (option == 0) 
    { 
      int i; 
      for (i = 1; i <= cont; i++)
      {
        printf("*");
      }
        return 0;
        exit(0);
    }
      
    if (option == 1)
    {
      first = newaluno(first); 
      cont+=1;
    }
    if (option==2)
    {
      scanf("%s",matriexclui);
      if (first== NULL){
       printf("Lista Vazia!\n");
      }   
      else {
      first = excluialuno(first, matriexclui);
      cont= cont-1;
      }
    }
    if (option== 3)
    {
      printaralu(first);
    }
    if (option==4){
      
      if (first== NULL){
       printf("Lista Vazia!\n");
  }   else {
      listainversa(first); 
  }
    }
  
    if (option==5)
    {
      printf("%d\n",cont);
    }
  }
  
}
