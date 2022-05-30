---
title : Stack
alias: Pilha
---

Ou **pilha**, estrutura na qual adicionamos e removemos elemento pela ordem de uma pilha, onde o último elemento colocado será o primeiro a ser retirado (LIFO), limitando assim a entrada dos dados à um único ponto.

Alguns métodos associados:
- **push** (coloca elemento no topo da lista);
- **pop** (remove elemento do topo);
- **peek** (obtêm o valor do topo sem o remover);
- **contains** (pesquisa por um elemento, retornando true ou false)

A recursão funciona com pilhas, pois quando uma função chama a si mesma, essa chamada é adicionada a uma pilha de processos, e quando essa pilha finalmente atinge o caso base, as funções vão sendo todas processadas de uma vez.

Implementação de uma pilha em javascript.

```js
class Stack {
constructor() {
  // We can also use linked list here
  this.items = [];
}
//inclui elementos no final da pilha
push(item) {
  this.items.push(item);
}
//remove último elemento adicionado
pop() {
  return this.items.pop();
}

size() {
  return this.items.length;
}
//lê o valor armazenado no topo da pilha
peek() {
  return this.items[this.items.length - 1];
}
//pesquisa por um elemento, retornando true ou false
contains(item) {
  return this.items.includes(item);
}

display() {
  return console.log(this.items);
}
}

const pilha = new Stack();
pilha.push(5);
pilha.push(12);
pilha.push(5); 
console.log(pilha.peek()); //5
console.log(pilha.pop()); //5
console.log(pilha.peek()); //12
console.log(pilha.size()); //2
pilha.contains(12); //true
pilha.display(); //[ 5, 12 ]
```

[Stack Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=I5lq6sCuABE)