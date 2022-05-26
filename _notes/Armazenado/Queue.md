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

<script src="https://gist.github.com/gio-bon/b05e9ddd7b66484957d4f912a778d9b5.js"></script>

[Queue Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=mDCi1lXd9hc)