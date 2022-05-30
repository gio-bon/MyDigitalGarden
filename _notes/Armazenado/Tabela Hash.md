---
title : Tabela Hash
alias: Dicionário, Tabela de Dispersão
---

É uma estrutura de dados que usa uma função hash para indicar onde armazenar os elementos (arrays e listas mapeiam diretamente para a memória, a tabela hash tem uma lógica adicional e mais inteligente)
- Chaves e valores
- São extremamente rápidas para pesquisar, inserir e remover itens
- Não precisa implementar pois as linguagens já a possuem
- Boas para pesquisas, pois mapeiam um objeto em relação a outro, como em uma lista telefônica ou no mapeamento de nomes de domínios para endereços IP (resolução DNS)
	- Filtram as duplicatas

Uso em caches (caching)
- Um buscador pode lembrar de dados pesquisados com frequência ao invés de recalculá-lo a cada solicitação
- Os dados do caching são armazenados em uma tabela hash
	- enderecosite/sobre -> dados da página sobre
	- enderecosite/contato -> dados da página de contato

## Função Hash
É uma função na qual você insere uma string e ela retorna um número (mais tecnicamente, ela mapeia strings e números)

Ex: a utilidade disso vem de, ao invés de procurar uma valor em um array de números, você escreve o nome do produto que quer saber o preço e a função hash retorna o seu preço (ou melhor, a posição exata do array em que o preço do produto está armazenado, assim o preço do abacate é sempre armazenado no índice 4)

## Colisões
A colisão é quando duas chaves são indicadas para o mesmo espaço. Se diversas chaves mapeiam para o mesmo espaço, podemos iniciar um lista encadeada naquele espaço. Mas se essa lista encadeada se tornar muito grande o desempenho da tabela ficará prejudicado.

Para evitar colisões é preciso
- um baixo fator de carga (índices ocupados dividido pelo total de índices no array) para que existam menos colisões; se esse índice for maior que 0,7 vai ser necessário o redimensionamento por criar um array maior e realocar os ítens.
- e uma boa função hash (SHA)

[Hash Table Data Structure - Illustrated Data Structures - YouTube](https://www.youtube.com/watch?v=jalSiaIi8j4)