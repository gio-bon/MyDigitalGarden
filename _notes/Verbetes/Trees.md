---
title : Trees
---

Ou árvores, consiste em uma série de nós vinculados conectados entre si para formar uma estrutura hierárquica de representação de dados. As informações ou os dados reais são armazenados nesses nós. Cada nó pode apontar para nenhum, um ou vários outros nós.

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

### Binary Search Tree
É uma variação da árvore padrão que tem três restrições que ajudam a organizar os dados.

Restrições
- Um nó pode ter no máximo dois filhos, o que ajuda a facilitar a pesquisa em toda árvore, à medida que não precisa perder tempo procurando em vários nós.
- Para cada nó pai, o filho à esquerda deve ter um valor menor ou igual a ele mesmo, e o filho da direita deverá ter um valor maior ou igual a ele mesmo.
- Dois nós não podem conter o mesmo valor

Vantagens da restrição: eficiência na pesquisa, pois é possível pesquisar nelas em tempo logarítmico, tornando a busca muito fácil devido à forma como ela é organizada (mesmo com grande quantidade de informações).

### Heaps
É uma árvore especial em que todos os nós pais são comparados com os nós filhos de uma maneira específica, por ser maior que e menor que. Essa implementação torna muito fácil inserir ou remover elementos. É usado no algoritmo heapsort.
- Heaps mínimos: o valor do nó raiz deve ser o menor em comparação com todos os seus nós filhos, sendo que essa ideia se transfere a todas as profundidades, o nó pai deve ser menor que seus filhos.
- Heaps máximos: o valor do nó raiz deve ser o maior em comparação com todos os seus nós filhos, sendo que essa ideia se transfere a todas as profundidades, o nó pai deve ser maior que seus filhos.

### Tries
Uma estrutura em forma de nó que armazenam letras de um alfabeto na forma de caracteres. Usado em para armazenar strings, o que permite recuperar rapidamente palavras na forma de string por percorrer um um caminho na árvore.

Aplicação em software preditivo de teclado, daqueles que conforme você digita ele vai dando opções para completar a palavra digitada.

### Graphs
A fazer.