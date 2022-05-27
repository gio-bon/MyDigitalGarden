---
title : Recursão
---

Recursão é um método de resolução de problemas que envolve quebrar um problema em subproblemas menores e menores até chegar a um problema pequeno o suficiente para que ele possa ser resolvido trivialmente. Normalmente recursão envolve uma função que chama a si mesma. Embora possa não parecer muito, a recursão nos permite escrever soluções elegantes para problemas que, de outra forma, podem ser muito difíceis de programar.

- Um algoritmo recursivo deve ter um **caso básico** (ponto de parada).
- Um algoritmo recursivo deve mudar o seu estado e se aproximar do caso básico.
- Um algoritmo recursivo deve chamar a si mesmo, recursivamente.

Exemplo em contagem regressiva com portugol.

```c
programa
{
	funcao contagemRecursiva(inteiro num){
		se(num == 0){  //caso base ou ponto de parada
			escreva(num)
		}
		senao{
			escreva(num, ", ") //resolve pequena parte do problema
			contagemRecursiva(num - 1) //é chamada a mesma função para resolver o problema (agora diminuído)
			}
		}
	
	funcao inicio()
	{
		inteiro numero
		escreva("Qual número quer regredir? ")
		leia(numero)
		contagemRecursiva(numero)
	}
}
```

Exemplo em descobrir o fatorial com portugol (**com** recursividade).
- Lembrando o fatorial de 6:  `6! = 1 x 2 x 3 x 4 x 5 x 6 = 720`

```c
programa
{
	funcao inteiro fatorial(inteiro num){
		se(num == 0 ou num == 1) //ponto de parada
			retorne 1
		senao{
			retorne num * fatorial(num - 1) //chamada recursiva
		}
	}
	
	funcao inicio()
	{	
	inteiro escolhaFat
	escreva("Entre com o fatorial: ")
	leia(escolhaFat)
	
	escreva("O fatorial de ", escolhaFat, " é ", fatorial(escolhaFat)) 
	}
}
```

Exemplo comparativo, em descobrir o fatorial com portugol (**sem** recursividade).

```c
programa
{
	funcao inicio()
	{
	
	inteiro escolhaFat, fatorial = 1
	escreva("Entre com o fatorial: ")
	leia(escolhaFat)
	
	para(inteiro num = 1; num <= escolhaFat; num++){
		fatorial = fatorial * num
	}
	escreva(fatorial)
	}
}
```

Fibonacci -> [exemplo](https://www.youtube.com/watch?v=Nxx7WqIDGCI&list=PLqJK4Oyr5WSgsSi26lXEm-SOnZkhkUO7k&index=4) de quando o uso de recursão não é uma boa ideia.