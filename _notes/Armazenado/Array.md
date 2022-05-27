---
title : Array
---

É uma lista de elementos semelhantes e do mesmo tipo, agrupados em um local central a fim de serem usados mais facilmente.

Atributos associados a arrays:
- **nome** -> que faz referência ao array;
- **tipo** -> cada array contendo elementos de um mesmo tipo de dados;
- **tamanho** -> a quantidade total de elementos que podem ser armazenados na matriz, atribuído em sua criação e não podendo ser alterado depois disso.

O **índices** de um elementos é um número inteiro que corresponde ao elemento dentro da matriz, que sempre começa no `0`. Servem para acessar ou alterar um elemento específico, geralmente com o nome do array seguido de seu índice.
Pode-se criar um array e já adicionar os elementos conhecidos ou criar um novo array, definir o número de elementos que terá, e ir populando o array conforme o uso.

**Matrizes paralelas** são duas ou mais matrizes com o mesmo número de elementos que tem a propriedade de que cada elemento em uma matriz está relacionado ao ao elemento de mesma posição em outras matrizes. São úteis para armazenar diferentes tipos de dados sobre a mesma entidade.
- Exemplo: em duas listas (nome e salário) o primeiro elemento  de ambas as listas, se refere à mesma pessoa (John tem salário de 10 mil)

Um array dentro de outro é conhecido como **array bidimensional** (usado para o processamento de imagens). A forma de acesso é igual aos arrays comuns, só que agora precisa-se de dois índices: `[coluna][linha]`. Existem também arrays de três e quatro dimensões.

**Prós**
- Bons para armazenar dados contíguos semelhantes.
- Acesso instantâneo às informações
- Muito mais simples do que outras estruturas (reduz a complexidade)

**Contras**
- O tamanho da matriz não pode ser alterado após sua inicialização
- Inserir e excluir dados pode demorar muito se estiver trabalhando com muitos dados
- Em uma grande lista estará desperdiçando espaço até que a preencha totalmente

Pode ser usada com segurança, mas para maiores funcionalidades há outras estruturas, como a [[ArrayList|Lista Encadeada]]

[Array Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=QJNwK2uJyGs)