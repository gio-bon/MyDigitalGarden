---
title : Buble Sort
---

![Buble Sort Gif](https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif)

Bubble sort é um algoritmo de ordenação que compara dois elementos adjacentes e os troca se não estiverem na ordem pretendida (ascendente vs descendente).

Tem [[Complexidade Quadrática]]. É uma maneira simples de classificar uma lista quando a complexidade não importa e um código curto e simples é o preferido.

Primeira iteração (compare e troque):
- A partir do primeiro índice, compare o primeiro e o segundo elementos;
- Se o primeiro elemento for maior que o segundo elemento, eles são trocados;
- Compare o segundo e o terceiro elementos;
- Se o segundo elemento for maior que o terceiro elemento, eles são trocados;
- Continue o processo acima até que o último elemento da matriz seja alcançado.

Iterações restantes:
- Continue o mesmo processo para as iterações restantes, de modo que, após cada iteração, o maior elemento entre os elementos não classificados seja colocado no final. Em cada iteração, a comparação ocorre até o último elemento não classificado.
- A matriz é classificada quando todos os elementos não classificados são colocados em suas posições corretas.

Exemplo em portugol.

```c
programa
{
	inclua biblioteca Util
	funcao inicio()
	{
		inteiro vetor[20], i, temp, mudanca = 1  //variáveis
		  
		//vai popular o vetor com números aleatórios
		para(i = 0; i < 20; i++){
			vetor[i] = Util.sorteia(1, 200)
			escreva(vetor[i], ", ") //mostra vetor desordenado
		}
		//algoritmo bubble sort
		enquanto(mudanca == 1){ //enquanto houver mudança o vetor é percorrido com o algo de ordenação
			mudanca = 0
			para(i = 0; i < 20 - 1; i++){
			se(vetor[i] > vetor[i+1]){
				temp = vetor[i]
				vetor[i] = vetor[i+1]
				vetor[i+1] = temp
				mudanca = 1 //se houver troca a mudança aconteceu
				}
			}
		}
		//para mostrar vetor ordenado
		  escreva("\n")
		para(i = 0; i < 20; i++){
			escreva(vetor[i], ", ")
		}
	}
}
```