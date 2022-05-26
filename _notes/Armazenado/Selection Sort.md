---
title : Selection Sort
---

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

<script src="https://gist.github.com/gio-bon/c4ad58baa4f24ee07ea7dbcc1208edd7.js"></script>

Exemplo em portugol.

<script src="https://gist.github.com/gio-bon/7f6b1d10ffc159c018af9c09c54a72e0.js"></script>