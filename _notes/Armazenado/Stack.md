---
title : Stack
---

Ou **pilha**, estrutura na qual adicionamos e removemos elemento pela ordem de uma pilha, onde o último elemento colocado será o primeiro a ser retirado (LIFO), limitando assim a entrada dos dados à um único ponto.

Alguns métodos associados:
- **push** (coloca elemento no topo da lista);
- **pop** (remove elemento do topo);
- **peek** (obtêm o valor do topo sem o remover);
- **contains** (pesquisa por um elemento, retornando true ou false)

A recursão funciona com pilhas, pois quando uma função chama a si mesma, essa chamada é adicionada a uma pilha de processos, e quando essa pilha finalmente atinge o caso base, as funções vão sendo todas processadas de uma vez.

Implementação de uma pilha em javascript.

<script src="https://gist.github.com/gio-bon/b2aa19e307f58daa97a0afc594a9915f.js"></script>

[Stack Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=I5lq6sCuABE)