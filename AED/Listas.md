## Lista sequencial

Listas são um dos tipos mais simples de estruturas de dados. Sua implementação, apesar de simples, é completa e possui uma vasta gama de implementações, desde sistemas operacionais, até mesmo IAs.
### Caracterização

- Representa a ordem linear entre os elementos;
- Se n = 0, a lista é vazia;
- É um objeto particularmente flexível, o seu número de elementos pode variar;
- Podem se homogêneas ou heterogenias;
- Lineares ou generalizadas;

Uma lista possui diversas implementações primitivas que permitem o seu funcionamento, e através delas é possível derivar outras funções que podem aumentar o nível de complexidade da lista, tornando ela mais útil.

Os elementos da lista serão dispostos sequencialmente, já que é a forma mais intuitiva de pensar em uma lista. O endereço de um nó poderá ser calculado com base no endereço do primeiro nó, se todos os nós ocuparem blocos de memória de mesmo tamanho. Logo, uma lista pode ser representada como um vetor unidimensional.

### Implementação

- Cria a lista corresponde a zerar o contador;
- O contador é testado para verificar se a lista é vazia, sendo o tamanho da mesma o valor do contador;
- Inserir um elemento na k-ésima posição exigirá abrir espaço, deslocando todos os elementos posteriores uma posição em direção ao fim da lista, atribuindo depois o valor novo no espaço livre obtido.
	- É necessário, também, verificar se a lista possui espaço disponível para realizar a inserção e se aquele espaço de memória disponível é válido ou não.
- Remover um elemento na k-ésima posição exige que todos os elementos posteriores sejam deslocados uma posição em direção ao início da lista, sobrescrevendo o elemento a ser removido.

![[Pasted image 20240813220459.png| center]]

## Lista encadeada

A lista encadeada apresenta algumas vantagens em cima da lista sequencial e possuindo apenas uma real desvantagem que, quando colocada no contexto da computação moderna, não é tão crítica assim, podendo ser desconsiderado.

- Bônus
	- A posição relativa dos elementos na memória não tem que corresponder estritamente à sua posição lógica na estrutura;
	- Os nós de uma lista encontram-se aleatoriamente disposto na memória;
	- Sendo interligados por referências, que indicam a posição do próximo elemento da lista.
	- Mais flexível
- Ônus
	- Maior gasto de memória, devido a necessidade de armazenar ponteiros.
	- Acréscimo de um campo em cada nó para armazenar uma referência da posição de seu sucessor.

![[Pasted image 20240813221747.png | center]]


### Implementação

A melhor forma de se implementar uma lista encadeada é através da utilização de alocação dinâmica. 

Na alocação encadeada dinâmica os nós de uma lista encontram-se aleatoriamente dispostos na memória e são interligados por ponteiros, que indicam a posição do próximo elemento da lista. 

Ao se implementar uma função de inserção, se faz necessário realizar algumas validações antes de realizar a ação:
- A posição é válida?
- Tem espaço na memória para armazenar mais um elemento?
- Qual a posição do nodo a ser inserido?
	- Primeiro ou não?

Ao se inserir um nodo no início da lista é necessário deslocar o ponteiro da referência externa, retirando-o do antigo primeiro nodo e apontando-o para o novo primeiro nodo. Esse novo primeiro nodo, por sua vez, irá ter um ponteiro apontando para a referência do antigo primeiro nodo, tornando-o, assim, o novo segundo nodo. Apesar de que ao se inserir um novo nodo, toda a lista é reorganizada, apenas é necessário mexer no ponteiro antecessor do novo nodo. 

![[Pasted image 20240813232123.png | center]]

No caso de a posição de inserção não ser a primeira da lista, se faz necessário o uso de um nodo auxiliar para armazenar a referência do nodo antecessor a posição onde está sendo inserido o novo nodo.

![[Pasted image 20240813232345.png | center]]

## Lista encadeada com nó cabeçalho
Ocasionalmente é desejável manter um  nó adicional no início de uma lista. Ele não representa um item na lista e é chamado de nó cabeçalho ou cabeçalho de lista. A parte inf deste nó é usada para manter informações globais sobre a lista, como o número de elementos na lista. 

### Implementação
A implementação dessa lista é quasi-similar a lista encadeada normal, com alguns *caviats*:

- Inserção:
	- É necessário levar em consideração o nó cabeçalho
![[Pasted image 20240826223525.png | center]]
- Remoção:
	- Também é necessário levar em consideração o nó cabeçalho
![[Pasted image 20240826223635.png | center]]

![[Pasted image 20240826224951.png | center]]

[[Filas e pilhas]]
