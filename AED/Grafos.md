![[Pasted image 20241117185810.png]]
- A sequência de nós é representada por {A, B, C, D, E, F, G, H};
- A relação (Arcos) entre cada nós (Vértices) é representada por {(A,B), (A,D), (A,C), (C,D), (C,F), (E,G), (A,A)} para um grafo n
- Vértices podem estar ou não conectados.

![[Pasted image 20241117185534.png]]
- Se o grafo for orientado, será representado por {<A,B>, <A,C>, <A,D>, <C,D>, <F,C>, <E,G>, <A,A>}
- Será chamado de dígrafo ou grafo orientado

### Grau
- O grau de um nó é a soma dos graus de entrada e saída
	- O grau de entrada é o número de arcos que chegam ao vértice
	- O grau de saída é o número de arcos que saem do vértice
- Ex.: O nó *C* possui Grau de entrada 2; Grau de saída 1;  Grau 3
### Relação
- Um nó *n* será adjacente a um nó m se existir um arco de m até n.
- Uma relação R num conjunto A é uma sequência de pares ordenados de elementos de A.
	- Ex.: Se A = {3, 5, 6, 8, 10, 17} e R = {<3,10>, <5,6>, <5,8>, <6,17>, <8,17>, <10,17>}, então existe um grafo tal que
	![[Pasted image 20241117190423.png]]
- A relação anterior pode ser descrita dizendo-se que, sendo <x,y> ∈ R, x está relacionado com y se x for menor que y e o resto obtido a partir da divisão de y por x for ímpar.

- Cada arco pode ter uma numeração *PESO*, a ser determinado através do resto da divisão entre x e y
- Um grafo com arcos numerados será chamado de *GRAFO PONDERADO*

### Caminho
- Existe um caminho entre a e b se existem n arcos conectando todos os vértices entre a e b e o vértice  n<sub>i</sub> e n<sub>i-1</sub> são adjacentes.
- Um arco do tipo {<x,y>, x=y} é chamado de ciclo
- Um grafo que possui ao menos um ciclo é chamado de *CÍCLICO*, caso contrário será um grafo *ACÍCLICO*
- Um grafo acíclico orientado é chamado de *DAG* (Directed acyclic graph)


- O grafo acima possui os tais caminhos:
	- Comprimento 1:
		- 3 - 10;
		- 10 - 17;
		- 5 - 8;
		- 5 - 6;
		- 8 - 17;
		- 6 - 17;
	- Comprimento 2:
		- 3 - 17;
		- 5 - 17

### Utilização
- Grafos podem ser codados utilizando vetores uni e bidimensionais.
- Os vetores bidimensionais serão utilizados quando o número de vértices for fixo, alterando apenas as relações entre eles, sem pesos ou outras informações ligadas aos arcos.

- Ex.:
```c
#define MAXNODES n

typedef struct {
	%% Informacores associadas a cada nodo %%
} node;
typedef struct {
	int adj;
} arc;
typedef struct {
	node nodes[MAXNODES];
	arc arcs[MAXNODES][MAXNODES];
} graph;

typedef struct graph g;
```

- O valor de adj\[i]\[j] será *TRUE* ou *FALSE*, dependendo de o nó *j* ser ou não adjacente ao nó *i*. O vetor bidimensional adj\[i]\[j] é chamado matriz de adjacência.

## Grafos Encadeados

Apesar da implementação matricial ser prática e de fácil implementação, ela comumente apresenta uma ineficiente gritante: A imutabilidade da matriz. Todos os espaços de arco serão utilizados, existam arcos entre nós ou não. Portanto uma outra abordagem se faz necessária.

Uma lista encadeada é a melhor representação de um grafo, seja ele dinâmico ou não. Pois podemos discernir se um nodo possui arcos ou não e por quais nodos aquele arco passa, além de ser mais eficiente pois não é necessário preencher todos os espaços de memória na sua concepção, tendo a liberdade de adicionar e remover nodos da estrutura.

Essa estrutura encadeada será definida da seguinte forma: 

```c
#define MAXNODES 500

typedef struct nodetype { 
	int info;
	int point;
	int next; 
}tipoNodo;

typedef tipoNodo listaDeNodos[MAXNODES];
```

Nesse caso, teremos um grafo constituído apenas por inteiros. Simplificando sua estrutura. Os nodos da lista poderão ser utilizados para armazenar as informações de cada nó, ao mesmo tempo que armazena as informações de cada arco.

No caso do nodo cabeçalho, *nodo\[p]* representará o vértice, *info* terá a informação do nodo, *point* apontará para o primeiro elemento da lista de nodos representando um arco emanando do vértice em questão, *next* terá a informação para o próximo vértice da lista de nodos.

No caso do nodo da lista, *nodo\[p]* representará um arco <x,y>, *info* terá a informação do peso do arco, *point* apontará para o nodo cabeçalho representando o nodo de grafo Y, *next* terá a informação para o próximo arco emanando de X.