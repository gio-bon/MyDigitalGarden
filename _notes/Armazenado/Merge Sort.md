---
title : Merge Sort
---

![Merge Sort Gif](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif)

Utiliza o conceito de dividir para conquistar, através da recursão. O funcionamento do Merge Sort baseia-se em uma rotina fundamental cujo nome é merge. Primeiro vamos entender como ele funciona e depois vamos ver como sucessivas execuções de merge ordena um array.

Tem a eficiência de *n log n* para todos os casos, o que é melhor que os métodos de ordenação bubble, selection e insertion sort.

Exemplos abaixo em portugol.

### Merge de dois arrays ordenados

```c
programa
{
	funcao inicio()
	{
		inteiro a[4] = {2, 4, 6, 8}
		inteiro b[4] = {1, 3, 5, 7}
		inteiro v[8]
		inteiro conta = 0
		inteiro i=0, j=0, k=0
		
		enquanto(conta < 8 e i <= 4 e j < 4){
			se(a[i] <= b[j]){
				v[k] = a[i]
				i++
				k++
				conta++
			}senao{
				v[k] = b[j]
				j++
				k++
				conta++
			}
		}
		//para alocar o último ítem de k
		enquanto(i < 4){
			v[k] = a[i]
			i++
			k++
		}
		enquanto(j < 4){
			v[k] = b[j]
			j++
			k++
		}
	}
}
```

### Merge em uma única lista

```c
programa
{
	funcao inicio()
	{
		inteiro a[8] = {2, 4, 6, 8, 1, 3, 5, 7}
		inteiro v[8]
		inteiro conta = 0
		inteiro comeco = 0, fim = 8- 1, meio = (comeco + fim)/2
		inteiro i = comeco, j = meio + 1, k = comeco
	
		enquanto(i <= meio e j <= fim){
			se(a[i] <= a[j]){
				v[k] = a[i]
				k++
				i++
			}senao{
				v[k] = a[j]
				k++
				j++
			}
		}
		//para alocar o último ítem de v
		enquanto(i <= meio){
			v[k] = a[i]
			i++
			k++
		}
		enquanto(j <= fim){
			v[k] = a[j]
			j++
			k++
		}
	}
}
```

### Merge Sort, usando Recursão
O algoritmo divide a lista logicamente em duas.
- Organiza a primeira parte (para ficar na ordem crescente) e depois a segunda (para ficar na ordem crescente)
- No fim chama a função merge para organizar a lista completa

```c
programa
{
	funcao inicio()
	{
		inteiro a[8] = {2, 4, 6, 8, 1, 3, 5, 7}
		inteiro v[8]
		inteiro conta = 0
		inteiro comeco = 0, fim = 8- 1, meio = (comeco + fim)/2
		inteiro i = comeco, j = meio + 1, k = comeco
	
		enquanto(i <= meio e j <= fim){
			se(a[i] <= a[j]){
				v[k] = a[i]
				k++
				i++
			}senao{
				v[k] = a[j]
				k++
				j++
			}
		}
		//para alocar o último ítem de v
		enquanto(i <= meio){
			v[k] = a[i]
			i++
			k++
		}
		enquanto(j <= fim){
			v[k] = a[j]
			j++
			k++
		}
	}
}
```