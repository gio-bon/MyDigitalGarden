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

```js
class Node {
  // constructor
  constructor(element) {
    this.element = element;
    this.next = null
  }
  }
  // linkedlist class
  class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  // adiciona um elemento no final da lista
  add(element) {
    // cria um novo nó
    var node = new Node(element);
    // para armazenar o nó atual
    var current;
    // se a lista estiver vazia adicione o elemento e torne-o cabeça
    if (this.head == null)
    this.head = node;
    else {
    current = this.head;
    // iterar até o final da lista
    while (current.next) {
      current = current.next;
    }
    // adicionar nó
    current.next = node;
    }
    this.size++;
  }

  // inserir elemento no índice de posição da lista
  insertAt(element, index) {
    if (index < 0 -- index > this.size)
    return console.log("Please enter a valid index.");
    else {
    // cria um novo nó
    var node = new Node(element);
    var curr, prev;
    curr = this.head;
    // adicione o elemento ao primeiro índice
    if (index == 0) {
      node.next = this.head;
      this.head = node;
    } else {
      curr = this.head;
      var it = 0;
      // itere sobre a lista para encontrar a posição para inserir
      while (it < index) {
      it++;
      prev = curr;
      curr = curr.next;
      }
      // adicionando o elemento
      node.next = curr;
      prev.next = node;
    }
    this.size++;
    }
  }

  // remove um elemento do local especificado
  removeFrom(index) {
    if (index < 0 -- index >= this.size)
    return console.log("Please Enter a valid index");
    else {
    var curr, prev, it = 0;
    curr = this.head;
    prev = curr;
    // deletando o primeiro elemento
    if (index === 0) {
      this.head = curr.next;
    } else {
      // iterar sobre a lista para a posição para remover um elemento
      while (it < index) {
      it++;
      prev = curr;
      curr = curr.next;
      }
      // remova o elemento
      prev.next = curr.next;
    }
    this.size--;
    // retorne o elemento de remoção
    return curr.element;
    }
  }

  // remove um determinado elemento da lista
  removeElement(element) {
    var current = this.head;
    var prev = null;
    // iterar sobre a lista
    while (current != null) {
    // comparando o elemento com o elemento atual, se encontrado, remova o e retorne true
    if (current.element === element) {
      if (prev == null) {
      this.head = current.next;
      } else {
      prev.next = current.next;
      }
      this.size--;
      return current.element;
    }
    prev = current;
    current = current.next;
    }
    return -1;
  }

  // encontra o índice do elemento
  indexOf(element) {
    var count = 0;
    var current = this.head;
    // iterar sobre a lista
    while (current != null) {
    // comparar cada elemento da lista com determinado elemento
    if (current.element === element)
      return count;
    count++;
    current = current.next;
    }
    // não encontrado
    return -1;
  }
  // verifica se a lista está vazia
  isEmpty() {
    return this.size == 0;
  }
  // dá o tamanho da lista
  size_of_list() {
    console.log(this.size);
  }
  // imprime os itens da lista
  printList() {
    var curr = this.head;
    var str = "";
    while (curr) {
    str += curr.element + " ";
    curr = curr.next;
    }
    console.log(str);
  }
}

// criando um objeto da classe Linkedlist
var ll = new LinkedList();

// testando isEmpty em uma lista vazia
console.log(ll.isEmpty()); // true

// adicionando elemento à lista
ll.add(10);

ll.printList(); // 10
console.log(ll.size_of_list()); // 1

// adicionando mais elementos à lista
ll.add(20);
ll.add(30);
ll.add(40);
ll.add(50);

ll.printList(); // 10 20 30 40 50

console.log("O elemento removido? " + ll.removeElement(40));

ll.printList(); // 10 20 30 50

console.log("Index of 40 " + ll.indexOf(40)); // -1
console.log("Index of 50 " + ll.indexOf(50)); // 3

ll.insertAt(60, 2); // insere 60 na segunda posição
ll.printList(); // 10 20 60 30 50 

console.log("is List Empty ? " + ll.isEmpty()); // false

// remover o 3º elemento da lista
console.log(ll.removeFrom(3));

ll.printList(); //10 20 60 50
```

[Linked List Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=odW9FU8jPRQ)