---
title : Pesquisa Binária
---

![](https://c.tenor.com/Jl0YrqxnHmAAAAAd/binary-search-sequence-search.gif)

Exemplo de algoritmo de busca binária em em portugol.

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