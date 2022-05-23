---
title : Insertion Sort
---

![](https://upload.wikimedia.org/wikipedia/commons/9/9c/Insertion-sort-example.gif?20110309111239)

A Ordenação por Inserção insere cada elemento da matriz em seu local apropriado com base em se a matriz está sendo classificada em ordem crescente ou decrescente.

A Ordenação por Inserção é um algoritmo de ordenação que coloca o elemento em seu local apropriado com base na ordem de ordenação. Um bom exemplo de ordenação por inserção é a classificação de cartas em suas mãos durante um jogo de cartas.

É de [[Complexidade Quadrática]]. É uma maneira simples de classificar uma lista quando a complexidade não importa e a lista que precisa ser classificada é curta.

- Suponha que o primeiro elemento da matriz seja classificado por propriedade;
- Armazene o segundo elemento da matriz em uma _cópia_;
- Compare _cópia_ com o primeiro elemento, se _cópia_ for menor que o primeiro elemento, então _cópia_ é colocado na frente do primeiro elemento;
- Armazene o próximo elemento não classificado do array em uma _cópia_;
- Compare _cópia_ com o elemento classificado e coloque-o no local apropriado em relação aos elementos classificados com base em _cópia_ ser menor ou maior que cada um dos elementos classificados;
- Continue com as etapas 4 e 5 até que todos os elementos da matriz sejam classificados.
- A matriz é classificada quando todos os elementos não classificados são colocados em suas posições corretas.

Exemplo em javascript.

<script src="https://gist.github.com/gio-bon/ef2f1f3a0a130439ae4e7b1b19399b9e.js"></script>

Exemplo com portugol.

<script src="https://gist.github.com/gio-bon/a4fe9d7f43b612090d7d3faef8c8c536.js"></script>