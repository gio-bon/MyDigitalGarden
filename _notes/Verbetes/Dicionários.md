---
title : Dicionários
---

Uma estrutura abstrata usada para uma ampla gama de propósitos, também chamada de mapas ou matriz associativas. Essa estrutura armazena seus elementos de dados na forma de pares de chave e valor.

É diferente das outras estruturas que geralmente usam índices para identificar um elemento. No caso dos dicionários, o que identifica um elemento é sua chave. As chaves podem ser de qualquer tipo de dados primitivo.

Restrições
- Cada chave só pode aparecer uma vez no dicionário.
- Cada chave pode ter apenas um valor.
- Pode existir duas chaves diferentes que apontam para o mesmo valor
- A maneira mais comum de implementar um dicionário é por meio de Tabela Hash, por onde elas são construídas.

[Hash Table Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=jalSiaIi8j4)

### Tabela Hash
São uma maneira de armazenar muitos dados de forma a reduzir os valores nulos enquanto continuam facilmente acessíveis.

Função Hash (*Hash Function*) pega todas as chaves de determinado dicionário e estrategicamente os mapeia em determinados locais de índice em uma matriz, para que possam ser recuperados com facilidade.