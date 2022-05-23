---
title : Buble Sort
---

![](https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif?20131109191607)

Bubble sort é um algoritmo de ordenação que compara dois elementos adjacentes e os troca se não estiverem na ordem pretendida (ascendente vs descendente).

Tem [[Complexidade Quadrática]]. É uma maneira simples de classificar uma lista quando a complexidade não importa e um código curto e simples é o preferido.

Primeira iteração (compare e troque):
- A partir do primeiro índice, compare o primeiro e o segundo elementos;
- Se o primeiro elemento for maior que o segundo elemento, eles são trocados;
- Compare o segundo e o terceiro elementos;
- Se o segundo elemento for maior que o terceiro elemento, eles são trocados;
- Continue o processo acima até que o último elemento da matriz seja alcançado.

Iterações restantes:
- Continue o mesmo processo para as iterações restantes, de modo que, após cada iteração, o maior elemento entre os elementos não classificados seja colocado no final. Em cada iteração, a comparação ocorre até o último elemento não classificado.
- A matriz é classificada quando todos os elementos não classificados são colocados em suas posições corretas.

Exemplo em javascript.

<script src="https://gist.github.com/gio-bon/9b9596f7298ad9c7938b71426d47e1f1.js"></script>

Exemplo em portugol.

<script src="https://gist.github.com/gio-bon/156beedfb464266a481abd255537f9c8.js"></script>