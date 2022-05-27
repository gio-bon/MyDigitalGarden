---
title : Queue
---

Ou **fila**, estrutura que seque o princípio de o primeiro a entrar é o primeiro a sair (FIFO) e segue muito dos princípios da pilha, com a diferença do local onde serão adicionados e removidos elementos, sendo adicionados pela cauta (*tail*) e removidos pela cabeça (*head*).
- Métodos comuns:
	- **enqueue** (adiciona no final da fila),
	- **dequeue** (remove elementos do começo da fila),
	- **peek** (retorna o objeto do começo da lista sem remover)
	- **contains** (retorna uma resposta true ou false para o elemento pesquisado dentro da fila)

Usado em SO em agendamento de tarefas, processo pelo qual o computador determina qual quais tarefas devem ser concluídas para o usuário. Também é usado em impressoras, para determinar quais páginas serão impressas primeiro.

Implementação de uma fila em javascript.

```js
class Queue {
  constructor() {
    this.items = [];
  }
  //adiciona no final da fila
  enqueue(item) {
    this.items.push(item);
  }
  //remove elementos do começo da fila
  dequeue() {
    return this.items.shift();
  }
  //retorna o tamanho da pilha
  size() {
    return this.items.length;
  }
  //mostra o primeiro item
  peek() {
    return this.items[0];
  }
  //diz se há o elemento na lista
  contains(item) {
    return this.items.includes(item);
  }

  display() {
    return console.log(this.items);
  }
}

const fila = new Queue();
fila.enqueue(51);
fila.enqueue(10);
fila.enqueue(13);
fila.display(); //[ 51, 10, 13 ]
console.log(fila.dequeue()); //51
console.log(fila.peek()); //10
console.log(fila.size()); //2
console.log(fila.contains(33)); //false
```

[Queue Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=mDCi1lXd9hc)