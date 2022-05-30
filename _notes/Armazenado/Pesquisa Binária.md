---
title : Pesquisa Binária
---

Pesquisa binária funciona dividindo uma lista ordenada, a cada passo, pela metade, até achar o item procurado. Diferente da busca sequencial, que vai do começo ao fim, sendo necessários diversos passos para achar se o item procurado (estiver no fim).

![](https://c.tenor.com/Jl0YrqxnHmAAAAAd/binary-search-sequence-search.gif)

Exemplo de algoritmo de busca binária em portugol.

```c
programa {
    	inclua biblioteca Util --> u
	funcao inicio() {
		inteiro lista[10] = {1, 2, 3 ,4 ,5, 7, 9, 10, 11, 12}
		//pesquisa pelo número e retornando o índice onde o números está
		inteiro resultado = PesquisaBinaria(12, lista)
		
		escreva(resultado)
	}
	funcao inteiro PesquisaBinaria(inteiro pesquisa, inteiro lista[]){
		inteiro baixo = 0
	     inteiro alto = u.numero_elementos(lista) - 1
	     
		enquanto(baixo <= alto){
		     inteiro meio = (baixo + alto) / 2
			inteiro chute = lista[meio]
	     	se(chute == pesquisa){
	     		retorne meio
	     	}
	     	se(chute > pesquisa){
	     		alto = meio - 1
	     	}senao{
	     		baixo = meio + 1
	     	}
	     }retorne -1 //-1 se não encontrado
	}
}
```

Exemplo de algoritmo de busca binária em C#.

```c#
using System;
using System.Collections.Generic;
using System.Linq;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var myList = new List<int> { 1, 3, 5, 7, 9 };
            Console.WriteLine(BinarySearch(myList, 3)); // => 1
            Console.WriteLine(BinarySearch(myList, -1)); // => null gets printed as an empty string
        }

        private static int? BinarySearch(IList<int> list, int item)
        {
            var low = 0;
            var high = list.Count() - 1;

            while (low <= high)
            {
                var mid = (low + high) / 2;
                var guess = list[mid];
                if (guess == item) return mid;
                if (guess > item)
                {
                    high = mid - 1;
                }
                else
                {
                    low = mid + 1;
                }
            }

            return null;
        }
    }
}
```