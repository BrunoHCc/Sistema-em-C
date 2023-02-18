#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define max 5
///////////////////////////////////////////////////////////////
//                                                 define tipos
///////////////////////////////////////////////////////////////
//                                            cria o tipo Prof
struct Prof{
    /*propriedade unica - reg_func*/
    int reg_func , data, telefones[2], salario;
    char cargo[50], nome[50], sexo, area[50], titulo[50], grad[50], email[2][50];
};

///////////////////////////////////////////////////////////////
//                                      cria o tipo Disciplinas
struct Disc{
     /*propriedade unica - sigla*/
    int numcred, cargahora;
    char sigla[4], nome[50], ementa[100], bibliografia[50];
};

///////////////////////////////////////////////////////////////
//                                  DECLARA FUNCOES ESPECIFICAS
///////////////////////////////////////////////////////////////
//			FUNCÇOES REALCIONADAS AOS PROFESSORES
///////////////////////////////////////////////////////////////
//         define a funcao verificadora ou de busca professores
int buscarprof(struct Prof professores[],int registro, int *tamanho)
{
    int i;
    for(i=0; i<=*tamanho; i++){
        if(professores[i].reg_func == registro){
            return i;
        }
    }
    return -1;
}

///////////////////////////////////////////////////////////////
//                  define a funcao de cadastro de professores
int cadastraprof(struct Prof professores[], int *posprof)
{
    int registro, achou, segundoemail, segundotelefone;
    printf("Digite o registro do professor: \n>>");
    scanf("%d",&registro);
    fflush(stdin);
    achou = buscarprof(professores, registro, posprof);
    if(achou == -1){
        professores[*posprof].reg_func = registro;
        printf("Digite o nome do professor\n>>");
        gets(professores[*posprof].nome);
        fflush(stdin);
        printf("Digite o data de nascimento do professor dia/mes/ano, apenas numeros! (01012004)\n>>");
        scanf("%d", &professores[*posprof].data);
        printf("Digite o sexo m (masculino) ou f (feminino)\n>>");
        scanf(" %c", &professores[*posprof].sexo);
        fflush(stdin);
        printf("Digite a area de pesquisa do professor\n>>");
        gets(professores[*posprof].area);
        printf("Digite a titulacao do professor\n>>");
        gets(professores[*posprof].titulo);
        printf("Digite a graduacao do professor\n>>");
        gets(professores[*posprof].grad);
        //adiciona emails
        printf("Digite o/os emails do professor (até 2)\n>>");
        gets(professores[*posprof].email[0]);
        fflush(stdin);
        printf("Deseja adicionar outro? Digite 1 para Sim, 2 para Não\n>>");
        scanf("%d", &segundoemail);
        fflush(stdin);
        if(segundoemail == 1){
        	printf(">>");
            gets(professores[*posprof].email[1]);
            fflush(stdin);
        }
        else{
        	strcpy(professores[*posprof].email[1],0);
		}
        //adiciona telefones
        printf("Digite o/os telefones do professor (até 2)(apenas numeros)\n>>");
        scanf("%d",&professores[*posprof].telefones[0]);
        printf("Deseja adicionar outro? Digite 1 para Sim, 2 para Não\n>>");
        scanf("%d", &segundotelefone);
        fflush(stdin);
        if(segundotelefone == 1){
        	printf(">>");
            scanf("%d", professores[*posprof].telefones[1]);
        }
        else{
        	professores[*posprof].telefones[1]=0;
		}
        fflush(stdin);
        (*posprof)++;
        return 1;
    }
    else{
        return -1;
    }
}
///////////////////////////////////////////////////////////////
//	 				   			  Listar todos os professeores
void listarTodosProf(struct Prof professores[], int *tamanho)
{
	int i,j,k;
	for (i=0;i<*tamanho;i++){
		printf("\nRegistro Funcional: %d \nNome: %s \nData de Nascimento: %d", professores[i].reg_func, professores[i].nome, professores[i].data);
		printf("\nSexo: %s \nArea de pesquisa: %s \nTitulacao: %s \nGraduacao: %s", professores[i].sexo, professores[i].area, professores[i].titulo, professores[i].grad);
		for(j=0;j<2;j++){
			printf("\nEmail: %s",professores[i].email[j]);
		}
		for(k=0;k<2;k++){
			printf("\nTelefone: %d", professores[i].telefones[k]);
		}
	}
}
///////////////////////////////////////////////////////////////
// 									  Listar um unico professor
void listarUmProf(struct Prof professores[], int *tamanho)
{
	int registro, achou, j, k;
	printf("\nDigite o registro do professor: \n>>");
    scanf("%d",&registro);
    fflush(stdin);
	achou = buscarprof(professores, registro, tamanho);
	if(achou!=-1){
		printf("\nRegistro Funcional: %d \nNome: %s \nData de Nascimento: %d", professores[achou].reg_func, professores[achou].nome, professores[achou].data);
		printf("\nSexo: %s \nArea de pesquisa: %s \nTitulacao: %s \nGraduacao: %s", professores[achou].sexo, professores[achou].area, professores[achou].titulo, professores[achou].grad);
		for(j=0;j<2;j++){
			printf("\nEmail: %s",professores[achou].email[j]);
		}
		for(k=0;k<2;k++){
			printf("\nTelefone: %d", professores[achou].telefones[k]);
		}
	}
	else
	printf("\nUsuario nao encontrado!\n");
}
///////////////////////////////////////////////////////////////
// 							Alterar o cadastro de um professor
void alterarProf(struct Prof professores[], int *tamanho)
{
	int registro, achou, segundoemail, segundotelefone;
	printf("\nDigite o registro do professor: \n>>");
    scanf("%d",&registro);
    fflush(stdin);
	achou = buscarprof(professores, registro, tamanho);
	if(achou!=-1){
        printf("\nDigite o nome do professor\n>>");
        gets(professores[achou].nome);
        fflush(stdin);
        printf("Digite o data de nascimento do professor dia/mes/ano, apenas numeros! (01012004)\n>>");
        scanf("%d", &professores[achou].data);
        printf("Digite o sexo m (masculino) ou f (feminino)\n>>");
        scanf(" %c", &professores[achou].sexo);
        fflush(stdin);
        printf("Digite a area de pesquisa do professor\n>>");
        gets(professores[achou].area);
        printf("Digite a titulacao do professor\n>>");
        gets(professores[achou].titulo);
        printf("Digite a graduacao do professor\n>>");
        gets(professores[achou].grad);
        //adiciona emails
        printf("Digite o/os emails do professor (até 2)\n>>");
        gets(professores[achou].email[0]);
        fflush(stdin);
        printf("Deseja adicionar outro? Digite 1 para Sim, 2 para Não\n>>");
        scanf("%d", &segundoemail);
        fflush(stdin);
        if(segundoemail == 1){
        	printf(">>");
            gets(professores[achou].email[1]);
            fflush(stdin);
        }
        else{
        	strcpy(professores[achou].email[1],0);
		}
        //adiciona telefones
        printf("Digite o/os telefones do professor (até 2)(apenas numeros)\n>>");
        scanf("%d",&professores[achou].telefones[0]);
        printf("Deseja adicionar outro? Digite 1 para Sim, 2 para Não\n>>");
        scanf("%d", &segundotelefone);
        fflush(stdin);
        if(segundotelefone == 1){
        	printf(">>");
            scanf("%d", professores[achou].telefones[1]);
        }
        else{
        	professores[achou].telefones[1]=0;
		}
	}
	else
	printf("\nUsuario nao encontrado!\n");
}
///////////////////////////////////////////////////////////////
// 							   excluir cadastro de um professor
int excluirProf(struct Prof professores[], int *tamanho)
{
	int registro, achou, i;
	printf("\nDigite o registro do professor: \n>>");
    scanf("%d",&registro);
    fflush(stdin);
	achou = buscarprof(professores, registro, tamanho);
	if(achou!=-1){
		for(i=achou;i<(*tamanho)-1;i++){
			professores[i] = professores[i+1];
		}
		(*tamanho)--;
		return 1;
	}
	else
		return -1;
}

///////////////////////////////////////////////////////////////
//		FUNÇOES RELACIONADAS ÀS DISCIPLINAS
///////////////////////////////////////////////////////////////
//                  define a funcao verificadora ou de busca de disciplinas
int buscardisc(struct Disc disciplinas[], char sigla[], int *tamanho){
    int i;
    char materia[4];
    
    for(i=0; i<*tamanho; i++){
    	strcpy(materia,disciplinas[i].sigla);
        if(strcmp(sigla,materia)==0){
            return i;
        }
    }
    return -1;
}

///////////////////////////////////////////////////////////////
//                  define a funcao de cadastro de disciplinas
int cadastradisc(struct Disc disciplinas[], int *posdisc)
{
	char sigla[4];
    int achou;
    fflush(stdin);
    printf("Digite a sigla da disciplina: \n>>");
    gets(sigla);
    fflush(stdin);
    achou = buscardisc(disciplinas, sigla, posdisc);
    if(achou == -1){
        strcpy(disciplinas[*posdisc].sigla,sigla);
        printf("Digite o nome da disciplina: \n>>");
        gets(disciplinas[*posdisc].nome);
        fflush(stdin);
        printf("Digite a ementa: \n>>");
        gets(disciplinas[*posdisc].ementa);
        printf("Digite a bibliografia: \n>>");
        gets(disciplinas[*posdisc].bibliografia);
        fflush(stdin);
        printf("Digite o numero de creditos: \n>>");
        scanf("%d", &disciplinas[*posdisc].numcred);
        printf("Digite a carga horaria: \n>>");
        scanf("%d", &disciplinas[*posdisc].cargahora);
        
        fflush(stdin);
        (*posdisc)++;
        return 1;
    }
    else{
        return -1;
    }
}

///////////////////////////////////////////////////////////////
//  								Listar todas as disciplinas
void listarTodasDisc(struct Disc disciplinas[], int *tamanho)
{
	int i;
	for (i=0;i<*tamanho;i++){
		printf("\nSigla: %s \nNome: %s \nEmenta: %s \nBibliografia: %s", disciplinas[i].sigla, disciplinas[i].nome, disciplinas[i].ementa, disciplinas[i].bibliografia );
		printf("\nNumero de creditos: %d \nCarga horaria: %d", disciplinas[i].numcred, disciplinas[i].cargahora);
	}
}

///////////////////////////////////////////////////////////////
// 										Listar uma disciplina
void listarUmaDisc(struct Disc disciplinas[], int *tamanho)
{
	char sigla[4];
	int achou;
	printf("\nDigite a sigla da disciplina: \n>>");
    gets(sigla);
    fflush(stdin);
	achou = buscardisc(disciplinas, sigla, tamanho);
	if(achou!=-1){
		printf("\nSigla: %s \nNome: %s \nEmenta: %s \nBibliografia: %s", disciplinas[achou].sigla, disciplinas[achou].nome, disciplinas[achou].ementa, disciplinas[achou].bibliografia );
		printf("\nNumero de creditos: %d \nCarga horaria: %d", disciplinas[achou].numcred, disciplinas[achou].cargahora);
	}
	else
	printf("\nDisciplina nao encontrada!\n");
}

///////////////////////////////////////////////////////////////
// 										Alterar uma disciplina
void alterarDisc(struct Disc disciplinas[], int *tamanho)
{
	char sigla[4];
	int achou;
	printf("\nDigite a sigla da disciplina: \n>>");
    gets(sigla);
    fflush(stdin);
	achou = buscardisc(disciplinas, sigla, tamanho);
	if(achou!=-1){
        printf("Digite o nome da disciplina\n>>");
        gets(disciplinas[achou].nome);
        fflush(stdin);
        printf("Digite a ementa\n>>");
        gets(disciplinas[achou].ementa);
        printf("Digite a bibliografia\n>>");
        gets(disciplinas[achou].bibliografia);
        fflush(stdin);
        printf("Digite a area de pesquisa do professor\n>>");
        scanf("%d", &disciplinas[achou].numcred);
        printf("Digite a titulacao do professor\n>>");
        scanf("%d", &disciplinas[achou].cargahora);
        fflush(stdin);
	}
	else
	printf("\nDisciplina nao encontrada!\n");
}

///////////////////////////////////////////////////////////////
// 										Excluir uma disciplina
int excluirDisc(struct Disc disciplinas[], int *tamanho)
{
	char sigla[4];
	int achou, i;
	printf("\nDigite a sigla da disciplina: \n>>");
    gets(sigla);
    fflush(stdin);
	achou = buscardisc(disciplinas, sigla, tamanho);
	if(achou!=-1){
		for(i=achou;i<(*tamanho)-1;i++){
			disciplinas[i] = disciplinas[i+1];
		}
		(*tamanho)--;
		return 1;
	}
	else
		return -1;
}

///////////////////////////////////////////////////////////////
//                                      DECLARA FUNCOES GERAIS
///////////////////////////////////////////////////////////////
//                                   define a funcao menu_prof
void menu_prof(struct Prof professores[], int *posprof)
{
    int opc=0, cadastrou;
	while(opc != 6){
		printf("\n\nMenu de professores: \n1.Cadastrar  2.Mostrar todos  3.Mostrar UM  4.Alterar  5.Excluir  6.Sair");
		printf("\nEscolha>> ");
        scanf("%d",&opc);
        if(opc == 1){
            cadastrou = cadastraprof(professores, posprof);
            if(cadastrou == 1){
                printf("O cadastro foi bem-sucedido!");
            }
            else
            printf("\nUsuario ja esta cadastrado\n");
        }
        else if (opc==2){
        	listarTodosProf(professores, posprof);
		}
		else if(opc==3){
			listarUmProf(professores, posprof);
		}
		else if(opc==4){
			alterarProf(professores, posprof);
		}
		else if(opc==5){
			int deletado;
			deletado = excluirProf(professores, posprof);
			if (deletado!=-1){
				printf("\nExcluido com sucesso\n");
			}
			else
			printf("\nProfessor nao localizado\n");
		}
		else
		printf("\nOpcao invalida\n");
    }
}

///////////////////////////////////////////////////////////////
//                                   define a funcao menu_disc
void menu_disc(struct Disc disciplinas[], int *posdisc)
{
	int opc=0, cadastrou;
	while(opc != 6){
		printf("\n\nMenu de disciplinas: \n1.Cadastrar  2.Mostrar todas  3.Mostrar UMA  4.Alterar  5.Excluir  6.Sair");
		printf("\nEscolha>> ");
        scanf("%d",&opc);
        if(opc == 1){
        	fflush(stdin);
            cadastrou = cadastradisc(disciplinas, posdisc);
            if(cadastrou == 1){
                printf("O cadastro foi bem-sucedido!");
            }
            else
            printf("\nDisciplina ja esta cadastrada\n");
        	}
	        else if (opc==2){
        	listarTodasDisc(disciplinas, posdisc);
		}
		else if(opc==3){
			fflush(stdin);
			listarUmaDisc(disciplinas, posdisc);
		}
		else if(opc==4){
			fflush(stdin);
			alterarDisc(disciplinas, posdisc);
		}
		else if(opc==5){
			int deletado;
			fflush(stdin);
			deletado = excluirDisc(disciplinas, posdisc);
			if (deletado!=-1){
				printf("\nExcluida com sucesso\n");
			}
			else
			printf("\nDisciplina nao localizada\n");
		}
		else
		printf("\nOpcao invalida\n");
    }
}
//////////////////////////////////////////////////////////////
// 												funcao MAIN
int main(){
    //cria um vetor de professores
    struct Prof professores[max];
    
    //cria um vetor de disciplinas
    struct Disc disciplinas[max];
    
    //declara variaveis
    int opc=0, codigo=0, achou=0, posprof = 0, posdisc = 0;

    //executa o menu principal enquanto opc for !=5
    while(opc != 5){
        system("cls");
        printf("\nMenu de opcoes: \n1.Professores  2.Disciplinas  3.Professores-Disciplina  4.Relatorios  5.Sair");
        printf("\nEscolha>> ");
        scanf("%d",&opc);

        //chama menu professores
        if(opc==1){
        	system("cls");
            menu_prof(professores, &posprof);
        }
        
        //chama menu Disciplinas
        else if(opc==2){
        	system("cls");
            menu_disc(disciplinas, &posdisc);
        }
    }
}

