---
title : LinkedList
---

 Lista encadeada ou lista ligada é uma estrutura em que cada elemento é um objeto separado chamado de nó, organizados de forma linear, onde os elementos são ligados uns aos outros, formando uma cadeia.

Cada nó tem duas partes:
- **Dados** ou informação armazenada, podendo ser de qualquer tipo primitivo
- **Referência** (ponteiro) que aponta para o endereço de memória do próximo nó da lista

Adicionar e remover dados não é tão simples pois nesta estrutura é possível remover e adicionar itens em qualquer ponto. Além disso, sempre que um nó é alterado devemos alterar seus ponteiros, o que pode ser complexo.

Geralmente são usadas no suporte a outras estruturas de dados, podendo ser usadas para fazer pilhas, filas e outras.

Tem como desvantagem de só poder avançar nos ponteiros, nunca retroceder ou desfazer. Esse problema é resolvido pelas Doubly-LinkedLists.

Implementação de uma lista ligada em javascript.

<script src="https://gist.github.com/gio-bon/6cfca47129936fa58361d35f0960c03c.js"></script>

[Linked List Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=odW9FU8jPRQ)