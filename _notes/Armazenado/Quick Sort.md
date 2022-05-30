---
title : Quick Sort
---

![](https://upload.wikimedia.org/wikipedia/commons/9/9c/Quicksort-example.gif)

Assim como o [[Merge Sort]], o quicksort usa divisão e conquista, portanto ele é um algoritmo recursivo.

- Escolha um elemento para servir como pivô.
- Ordene o array de forma que todos os elementos menores que o pivô fiquem à esquerda e todos os elementos maiores que o pivô fiquem à direita.
- Execute o algoritmo recursivamente, levando em consideração o pivô anterior para subdividir adequadamente os arrays esquerdo e direito. 

Implementação em portugol:

```c
programa
{
	
inclua biblioteca Util
	funcao inicio()
	{
		inteiro arr[] = {6, 2, 5, 3, 8, 7, 1, 4, 100, 1000, 9}
		inteiro tamanho = Util.numero_elementos(arr)
		QuickSort(arr, 0, tamanho - 1)
		
		//imprime resultado final
		para(inteiro c = 0; c < tamanho; c++){
			escreva(arr[c], ", ")
		}
		
	}
	funcao QuickSort(inteiro arr[], inteiro start, inteiro end){
		se(start < end){
			inteiro pivot = Particao(arr, start, end)
			//chamadas recursivas
			QuickSort(arr, start, pivot -1)
			QuickSort(arr, pivot + 1, end)
		}
	}
	funcao inteiro Particao(inteiro arr[], inteiro start, inteiro end){
		inteiro pivot = end, i = start - 1, j = start

		enquanto(j < pivot){
			se(arr[j] > arr[pivot]){
				j++
			}senao{
				i++
				Swap(arr, j, i)
				j++
			}
		}
		Swap(arr, i + 1, pivot)
		retorne i+1
	}
	funcao Swap(inteiro arr[], inteiro firstIndex, inteiro secondIndex){
		inteiro temp = arr[firstIndex]
		arr[firstIndex] = arr[secondIndex]
		arr[secondIndex] = temp
	}
}

```