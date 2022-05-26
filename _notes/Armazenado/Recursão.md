---
title : Recursão
---

Recursão é um método de resolução de problemas que envolve quebrar um problema em subproblemas menores e menores até chegar a um problema pequeno o suficiente para que ele possa ser resolvido trivialmente. Normalmente recursão envolve uma função que chama a si mesma. Embora possa não parecer muito, a recursão nos permite escrever soluções elegantes para problemas que, de outra forma, podem ser muito difíceis de programar.

- Um algoritmo recursivo deve ter um **caso básico** (ponto de parada).
- Um algoritmo recursivo deve mudar o seu estado e se aproximar do caso básico.
- Um algoritmo recursivo deve chamar a si mesmo, recursivamente.

Exemplo em contagem regressiva com portugol.

<script src="https://gist.github.com/gio-bon/cbfa9e5a9ffc8c32766faf1f1bfcc990.js"></script>

Exemplo em descobrir o fatorial com portugol (**com** recursividade).
- Lembrando o fatorial de 6:  `6! = 1 x 2 x 3 x 4 x 5 x 6 = 720`

<script src="https://gist.github.com/gio-bon/efe979aac3eedea21539f20b3155899d.js"></script>

Exemplo comparativo, em descobrir o fatorial com portugol (**sem** recursividade).

<script src="https://gist.github.com/gio-bon/ee92f1d0aa90219f0c17ed0c72a5bfca.js"></script>

Fibonacci -> [exemplo](https://www.youtube.com/watch?v=Nxx7WqIDGCI&list=PLqJK4Oyr5WSgsSi26lXEm-SOnZkhkUO7k&index=4) de quando o uso de recursão não é uma boa ideia.