# Aloca-o-dinamica-com-struct-C
Alocação dinamica com struct C


#include <stdlib.h>
#include <string.h>
#include <stdio.h>

typedef struct funcionario{
 int codigo;
 int horas_t;
 float valor_h;
}Func;

typedef struct aluno{
  char nome[30];
  int RA;
  float media;
}Aluno;

int main(){
  //Cadastro Aluno no seguimento Stack
  printf("Cadastro Aluno no seguimento Stack....\n");
  Aluno aluno, *ptr;
  aluno.RA = 12345;
  strcpy(aluno.nome,"Joao");
  aluno.media = 8.0;
  ptr = &aluno;

  printf("%d\t%s\t%.1f\n", (*ptr).RA, (*ptr).nome, (*ptr).media);
 
  printf("%d\t%s\t%.1f\n", ptr->RA, ptr->nome, ptr->media);

  //Cadastro Aluno no seguimento Heap
  printf("Cadastro Aluno no seguimento heap....\n");
  Aluno *ptr2 = (Aluno*) malloc(sizeof(Aluno));
  ptr2->RA = 12345;
  strcpy(ptr2->nome,"Joao");
  ptr2->media = 8.0;
  printf("%d\t%s\t%.1f\n", ptr2->RA, ptr2->nome, ptr2->media);


//Cadastro Funcionario (heap);
  printf("Cadastro Funcionario no seguimento heap....\n");
  Func* F = (Func*) malloc(sizeof(Func));
  F->codigo = 10;
  F->horas_t = 160; //160h no mes
  F->valor_h = 26.50;

  printf("Codigo: %d\tR$%.2f\n",F->codigo, (F->horas_t*F->valor_h));


  //Vetor de alunos com alocação dinâmica
   //Cadastro Aluno no seguimento Heap
  printf("Cadastro Aluno no seguimento heap....\n");
  Aluno *vAluno = (Aluno*) malloc(2*sizeof(Aluno));
  vAluno[0].RA = 1234;
  vAluno[0].media = 9.0;
  strcpy(vAluno[0].nome,"Joao");
  printf("%d\t%s\t%.1f\n", vAluno->RA, vAluno->nome, vAluno->media);
 
 vAluno[1].RA = 56789;
  vAluno[1].media = 7.0;
  strcpy(vAluno[1].nome,"Paulo");
  printf("%d\t%s\t%.1f\n", vAluno[0].RA, vAluno[0].nome, vAluno[0].media);

   printf("%d\t%s\t%.1f\n", vAluno[1].RA, vAluno[1].nome, vAluno[1].media);
 
 
  return 0;
}
