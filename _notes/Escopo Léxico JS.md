---
title: Escopo Léxico JS
---

Escopo é a acessibilidade de objetos, variáveis e funções em diferentes partes do código. Em outras palavras, o escopo é quem determina quais são os dados que podem ser acessados em uma determinada parte do código.

### Local
Tudo que é declarado dentro de uma função.

### Global
Escopo global é tudo o que for declarado, criado fora de blocos `{ }` e de funções, por conta disso toda a nossa aplicação tem acesso a eles.

### De bloco
Um bloco é o que está dentro de `{ }`, assim escopo de bloco é que tudo o que está dentro de um bloco não é acessível fora dele.

No JS em especifico até o ES2016 (ECMAScript2016), tínhamos um grande problema ao declarar variáveis usando `var` dentro de blocos de instrução (IF, FOR, WHILE, etc...) pois esses blocos não criam o seu próprio escopo, o que fazia com que todas as variáveis declaradas com `var` dentro dele se tornassem globais. Por conta disso evitamos ao máximo o uso da `var`, pois a `let` nasceu dessa necessidade de podermos declarar variáveis com escopo local dentro de blocos de instrução.

Veja [[Closure JS]]