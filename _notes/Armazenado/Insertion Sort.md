---
title : Insertion Sort
---

![Insertion Sort Gif](https://upload.wikimedia.org/wikipedia/commons/9/9c/Insertion-sort-example.gif)

A Ordenação por Inserção insere cada elemento da matriz em seu local apropriado com base em se a matriz está sendo classificada em ordem crescente ou decrescente.

A Ordenação por Inserção é um algoritmo de ordenação que coloca o elemento em seu local apropriado com base na ordem de ordenação. Um bom exemplo de ordenação por inserção é a classificação de cartas em suas mãos durante um jogo de cartas.

É de [[Complexidade Quadrática]]. É uma maneira simples de classificar uma lista quando a complexidade não importa e a lista que precisa ser classificada é curta.

- Suponha que o primeiro elemento da matriz seja classificado por propriedade;
- Armazene o segundo elemento da matriz em uma _cópia_;
- Compare _cópia_ com o primeiro elemento, se _cópia_ for menor que o primeiro elemento, então _cópia_ é colocado na frente do primeiro elemento;
- Armazene o próximo elemento não classificado do array em uma _cópia_;
- Compare _cópia_ com o elemento classificado e coloque-o no local apropriado em relação aos elementos classificados com base em _cópia_ ser menor ou maior que cada um dos elementos classificados;
- Continue com as etapas 4 e 5 até que todos os elementos da matriz sejam classificados.
- A matriz é classificada quando todos os elementos não classificados são colocados em suas posições corretas.

Exemplo em javascript.

```js
function insertionSort(array) {
	for (let i = 1; i < array.length; i++) {   // assumimos que o primeiro elemento do array já está ordenado e começamos a iteração a partir do segundo elemento do array;
	  let key = array[i];   // defina o próximo elemento de array não classificado para igual chave;
		let j = i - 1;   // defina o último elemento classificado como igual a j;
		while (j >= 0 && array[j] > key) {   // verifique se a chave atual é menor que o último elemento classificado;
			array[j + 1] = array[j];   // se estiver, mova o último elemento ordenado para a direita (abrindo espaço para a chave atual);
		j--;   // passar para o próximo elemento classificado;
	  }
	  array[j + 1] = key;   // se a chave atual for maior que o último elemento classificado, coloque-a à direita do último elemento classificado;
	}
	return array;
}
```

Exemplo com portugol.

```c
programa
{
	inclua biblioteca Util
	funcao inicio()
	{
		inteiro vetor[7], p, copia, tam = 7, indice  //variáveis
		  
		//vai popular o vetor com números aleatórios
		para(p = 0; p < 7; p++){
			vetor[p] = Util.sorteia(1, 200)
			escreva(vetor[p], ", ") //mostra vetor desordenado
		}
		//algo insertion sort
		para(inteiro i = 0; i < tam; i++){
			copia = vetor[i]
			indice = i
	
			enquanto(indice > 0 e vetor[indice - 1] > copia){
				vetor[indice] = vetor[indice - 1]
				indice--
			}
			vetor[indice] = copia
		}
		
		//mostra vetor ordenado
		escreva("\n")
		para(p = 0; p < 7; p++){
			escreva(vetor[p], ", ")
		}
	}
}
```