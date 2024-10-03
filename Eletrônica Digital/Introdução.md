## O que é eletrônica?

- É o estudo do movimento dos elétrons em semicondutores (Componentes eletrônicos).
- Ciência que estuda as formas de utilização da energia elétrica para **representar**, **armazenar**, transmitir ou **processar** dados.

## Duas eletrônicas

- Eletrônica analógica
	- Tem valores/estados que variam de modo contínuo (vida real).
	- Possui sinal analógico que pode assumir infinitos valores em um intervalo de tempo
- Eletrônica digital
	- Apenas dois valores/estados possíveis, tornando o controle mais simples (processamento, transmissão e armazenamento).
	- Possui sinal digital que só pode assumir dois valores em um intervalo de tempo

## Sistemas digitais
- Um conjunto de componentes eletrônicos;
- Um sistema que processa e manipula dados digitais;
- Utilizados em uma ampla gama de aplicações;
- Sistemas computacionais e eletrônicos de consumo;

Os sistemas digitais gerenciam a complexidade aplicando a regra dos 3 y's e abstração
- Hierarchy
	- Sistema dividido em módulos ou submódulos;
- Modularity
	- Funções e interfaces bem definidas;
- Regularity
	- Que os módulos sejam facilmente reutilizados;

### O que é abstração?
- O processo de simplificar e ocultar os detalhes complexos;
- Facilita o design, análise e verificação de sistemas;
- Permite a criação de sistemas modulares;
- Permite o uso de componentes prontos e testados;

![[exemplos.png | center | 400]]

Sistemas digitais consideram apenas dois valores discretos (dígitos) 1's (true ou high) e 0's (false ou low), para isso utilizam níveis de voltagem para determinar seu estado. Cada dígito é denominado de bit (binary digit).


### Onda digital

![[Onda.png | center]]

 Na onda digital é possível estudar três aspectos de seu comportamento:
- Frequência;
	- O número de ciclos completos que a onda realiza por segundo (Hz);
- Período;
	- O tempo necessário para que a onda complete um ciclo completo (intervalo entre dois pontos equivalentes);
- Tempo do bit;
	- Duração necessária para transmitir um único bit;
	- Determina se a onda é síncrona ou não;

![[Ciclo.png | center]]

Com esses três aspectos é possível determinar seu ciclo de trabalho utilizando a largura do pulso (t<sub>w</sub>) e o Período (T) que pode ser descrito como o inverso da frequência. 

![[Periodo.png | center]]

A onda digital acima está com o seu período explicitado. O período é onde se dá dois sinais iguais, nesse caso dois sinais de borda de subida/positiva

![[TempoBit.png | center]]

Aqui está representado uma onda assíncrona

![[TempoBItClock.png | center]]

Aqui está representada uma onda síncrona om o seu clock
