---
title : Recursão
---

Recursao tem o caso base, que diz quando a recursão deve parar, e o caso recursivo, que é quando a função chama a si mesma.

Exemplo em contagem regressiva com portugol.

```c
programa
{
	funcao inicio()
	{
		inteiro numeroRegredir
		//lê um número que será regredido
		leia(numeroRegredir)
		enquanto(numeroRegredir >= 1){
			numeroRegredir = Regressao(numeroRegredir)
		}
	}
	funcao inteiro Regressao(inteiro entrada){
		escreva(entrada - 1, ", ")
		retorne entrada--
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

![](http://luizricardo.org/wordpress/wp-content/upload-files/2016/04/top-5-programming-animated-gifs_recursion-animted-gif.gif)

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