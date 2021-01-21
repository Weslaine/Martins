# Martins
#include <iostream> //stdio.h
#include <map>
#include <locale.h>
using namespace std;

struct Materias{
	string codigo;
	string disciplina;
};

int main(){	
	setlocale(LC_ALL, "Portuguese");

	int chave;	
	char codigo[3];
	char disciplina[100]; 
	map<int, Materias> MapaLista;
	Materias mat;
	
	mat.codigo = "103";
	mat.disciplina = "Estrutura de Dados I";
	MapaLista[1] = mat;
	
	mat.codigo = "104";
	mat.disciplina = "Estrutura da Dados II";
	MapaLista[2] = mat;
	
	printf("Informe a chave da próxima disciplina: ");
	scanf("%d", &chave);
	printf("\nChave informada: %d", chave);	
	
	if (MapaLista.find(chave) != MapaLista.end()){
		cout<<"\nChave já cadastrada!"<<endl;		
	}else{		
		fflush(stdin);		
		printf("\nInforme o código da disciplina: ");
		gets(codigo);
		mat.codigo = codigo;
		
		printf("\nInforme o nome da disciplina: ");
		gets(disciplina);
		mat.disciplina = disciplina;
		fflush(stdin);
		MapaLista[chave] = mat;
	}
	printf("\nImpressão de todos dos elementos do mapa!\n");
	/*imprimir ******/
	for(unsigned int i = 1; i<=MapaLista.size(); i++){
		cout<<"\nCódigo: "+MapaLista[i].codigo +
			" Disciplina: "+MapaLista[i].disciplina<<endl;
	}	
	return 0;
}
