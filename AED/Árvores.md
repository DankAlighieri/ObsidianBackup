## Árvore binária de busca
## Árvore AVL

## Fator de desbalanceamento
FB = H(d) - H(e)
### Rotação
- Rotação à esquerda
	- Feita quando há um fator de desbalanceamento > 0
	- Solução:
		- Filho da direita vira nova raiz
		- Raiz original vira filho da esquerda da nova raiz
		- Se o filho da direita possuir filho a esquerda, ele vira filho da direita do filho a esquerda

![[Pasted image 20241013203632.png || center]]

- Rotação à direita
	- Feita quando há um fator de desbalanceamento < 0
	- Solução:
		- Filho da esquerda vira nova raiz
		- Raiz original vira filho a direita da nova raiz
		- Se o antigo filho a esquerda da raiz possuir filho a direita, ele vira filho a esquerda do filho a direita da nova raiz

![[Pasted image 20241013203808.png || center]]

- Rotação dupla
	- Feita quando o FB do nó filho com valor +/-1 possuir sinal oposto ao FB do pai (FB = +/- 2)
	- Solução: 
		- Depende o sinal dos desbalanceamentos.
			- Caso +/-
				- Rotação à direita na sub-árvore da direita
				- Rotação à esquerda na árvore original.
			- Caso -/+
				- Rotação à esquerda na sub-árvore da esquerda
				- Rotação à direita na árvore original.