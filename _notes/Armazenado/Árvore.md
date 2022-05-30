---
title : Árvore
---

Ou árvores, consiste em uma série de nós vinculados conectados entre si para formar uma estrutura hierárquica de representação de dados. As informações ou os dados reais são armazenados nesses nós. Cada nó pode apontar para nenhum, um ou vários outros nós.

O problema da [[Pesquisa Binária]] é que ao inserir um novo elemento você deve reorganizar a lista (porque funciona apenas se estiver organizada). A ideia de árvore é inserir ítens em uma lista sem precisar reorganizá-los.

- Não é possível usar de acesso aleatório
- Seu desempenho de execução depende fortemente de estar balanceada
	- Àrvore vermelho-preto (rubro negra) se balanceiam automaticamente
- Comumente usadas em armazenamento em bancos de dados
- Estruturas mais avançadas: árvores B, árvore rubro negra, heaps, árvores splay (espalhadas)

Termos
- **Vértice** é um nó na árvore
- **Aresta** é a conexão entre os nós

Relacionamentos
- **Raiz** (root node) é o começo da árvore, seu primeiro nó
- Nó **filho** (child node) e Nó **pai** (parent node)
- Nó **folha** (leaf node) um nó que não tem filhos

Propriedades
- **Altura** (height) é uma propriedade da árvore, o número de arestas mais longo em uma árvore.
- **Profundidade** (depth) é uma propriedade dos nós, o número de arestas em relação ao root node, se uma aresta do root então a profundidade é 1, se dois, a profundidade é 2 ...

Usos no armazenamento de dados devido à sua estrutura hierárquica natural. Ao impor **regras e restrições** à estrutura de árvores, sobre a forma como elas devem armazenar dados, faz com que elas se tornam ainda mais úteis.

Binary Search Tree
Heaps
Tries
Grafos