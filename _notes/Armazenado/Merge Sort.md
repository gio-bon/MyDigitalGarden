---
title : Merge Sort
---

![](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif?20151222172210|200)

Utiliza o conceito de dividir para conquistar, através da recursão. O funcionamento do Merge Sort baseia-se em uma rotina fundamental cujo nome é merge. Primeiro vamos entender como ele funciona e depois vamos ver como sucessivas execuções de merge ordena um array.

Tem a eficiência de *n log n* para todos os casos, o que é melhor que os métodos de ordenação bubble, selection e insertion sort.

Exemplos abaixo em portugol.

### Merge de dois arrays ordenados

<script src="https://gist.github.com/gio-bon/e5245e4604194260f95edd76df7f4745.js"></script>

### Merge em uma única lista

<script src="https://gist.github.com/gio-bon/3fc1283ae7d2c50effce8860d79b6850.js"></script>

### Merge Sort, usando Recursão
O algoritmo divide a lista logicamente em duas.
- Organiza a primeira parte (para ficar na ordem crescente) e depois a segunda (para ficar na ordem crescente)
- No fim chama a função merge para organizar a lista completa

<script src="https://gist.github.com/gio-bon/760e226459f424f7cd4c44eee6bbc0fb.js"></script>