---
title : Selection Sort
---

<img src="https://www.doabledanny.com/static/1f66c277a7a820e3492149c6e499bdb1/2.gif" width="500">


![](https://www.doabledanny.com/static/1f66c277a7a820e3492149c6e499bdb1/2.gif)

A ordenação por seleção é um algoritmo de ordenação que divide a lista de entrada em duas partes, uma sublista ordenada que é construída da esquerda para a direita e uma sublista dos valores não ordenados restantes. A sublista ordenada é colocada na frente (à esquerda) da sublista não ordenada.

É de [[Complexidade Quadrática]], uma maneira simples de classificar uma lista quando a complexidade não importa e a lista que precisa de classificação é curta.

- Defina o primeiro elemento da matriz como _menor_;
- Compare _menor_ com o segundo elemento, se o segundo elemento for menor que _menor_, atribua o segundo elemento como _menor_, caso contrário, não faça nada;
- Compare _menor_ com o elemento a seguir, se esse elemento for menor que _menor_, atribua _menor_ a esse elemento, caso contrário, não faça nada;
- Continue o passo 3 acima até que o último elemento seja alcançado;
- Mova _menor_ para a frente do array e mova o limite da sublista um elemento para a direita (porque agora há um elemento presente na sublista ordenada, enquanto a sublista não ordenada ficou menor em um elemento);
- Continue com os passos 3 - 5, até que todos os elementos estejam em suas posições ordenadas.
- A matriz é classificada quando todos os elementos não classificados são colocados em suas posições corretas.

Exemplo em javascript.

```js
function selectionSort(array) {
	for (let i = 0; i < array.length - 1; i++) { // for itera através de cada item na matriz, parando com o penúltimo item. Isso ocorre porque no próximo loop vamos comparar `i` com seu vizinho `i + 1` no array, portanto, temos que parar este loop inicial um índice antes do tamanho completo do array;
	  let minimum = i; // defina o primeiro elemento como `mínimo`;
	  for (let j = i + 1; j < array.length; j++) { // o loop for itera através de cada item na sublista não classificada;
		if (array[j] < array[minimum]) { // if verifica se o seguinte elemento da sublista não classificada é menor que o atual `mínimo`;
		  minimum = j; // se for, atribua `minimum` a esse elemento ; caso contrário, não faça nada;
		}
	  }
	  [array[i], array[minimum]] = [array[minimum], array[i]]; //  mova `minimum` para o final da sublista ordenada;
	}
	return array;
}
```

Exemplo em portugol.

```c
programa
{
	inclua biblioteca Util
	funcao inicio()
	{
		inteiro vetor[7], p, temp, tam = 7, menor  //variáveis
		  
		//vai popular o vetor com números aleatórios
		para(p = 0; p < 7; p++){
			vetor[p] = Util.sorteia(1, 200)
			escreva(vetor[p], ", ") //mostra vetor desordenado
		}
		//algo selection sort
		para(inteiro i = 0; i < tam - 1; i++){ //começa na primeira posição e vai indo pra direita
			menor = i
			para(inteiro j = i; j < tam; j++){ //compara do começo e percorre comparando pra direita
				se(vetor[j] < vetor[menor])
					menor = j
			}
			//troca as posições
			temp = vetor[menor]
			vetor[menor] = vetor[i]
			vetor[i] = temp
		}
		  
		  //mostra vetor ordenado
		escreva("\n")
		para(p = 0; p < 7; p++){
			escreva(vetor[p], ", ")
		}
	}
}
```