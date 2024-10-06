## Filas
- A fila é uma estrutura de dados que possui uma disciplina de acesso que caracteriza a forma como ela se comporta. A sua disciplina de acesso é conhecida como FIFO (First in First out).
- A fila pode ser vista como uma lista simplificada, aceitando inserções apenas no final e remoções apenas no início. Não há opção de abandono da fila.
- Possui apenas dois tipos de implementações: Sequencial ou encadeada.

![[Pasted image 20241003193920.png || center]]
### Fila sequencial
Uma fila sequencial se utiliza da praticidade dos vetores. Mas se faz necessário ter controle do seu início e fim, para que seja possível manipular a fila, sem perder a sequencialidade. A conveniência de possuir um ponteiro N que contém o número de elementos da fila também 

A fila será implementada sobre um vetor circular para impedir falhas de segmentação.

![[Pasted image 20241003195409.png]]

Quando o cursor (ou índice de inserção) atinge a última posição (MAX - 1), em vez de avançar para uma posição inexistente, ele volta para o início (posição 0). Ou seja, a fila "circular" se repete. Isso ajuda a usar o espaço de forma eficiente. 

- Quando k (posição) < Max, k%MAX = k 
- Quando K = MAX, k % MAX = 0, ou seja, volta para o começo da fila.




## Próximo conteúdo
>[[Árvores]]
