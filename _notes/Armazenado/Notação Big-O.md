---
title : Notação Big-O
---

- Importante para saber quão rápido e eficiente um algoritmo é, sendo a forma de julgar diferentes estruturas de dados, ajudando a definir quando usar (ou não) determinada estrutura.
- Não basta saber quanto tempo um algoritmo leva para ser executado, você precisa saber se o tempo de execução aumenta conforme a lista aumenta. O quão rapidamente o tempo de execução aumenta conforme aumenta-se o número de elementos.
- Compara o número de operações e não o tempo. *O(n)* onde n é o número de operações.
- Medimos a eficiência ou velocidade de uma estrutura de dados com base em quão bem ela pode realizar quatro tarefas básicas, como acessar, pesquisar, inserir ou excluir elementos em seus dados.
- Sempre leva em conta o pior caso (ex. se o nome procurado for o último da lista, não o primeiro)

## Tempos de execução
Sempre que falo sobre um algoritmo, falo sobre o seu tempo de execução. Geralmente, você escolhe o algoritmo mais eficiente, caso esteja tentando otimizar tempo e espaço.

Aqui temos cinco tempos de execução Big O que você encontrará bastante:

Pesquisa sequencial sigifica verificar número por número. Se for uma lista de 100 números, precisaríamos de 100 tentativas. Se fosse uma lista de 4 bilhões de números, precisaríamos de 4 bilhões de tentativas. Logo, o número máximo de tentativas é igual ao tamanho da lista. Isso é chamado de **tempo linear**. *O(n)*

A [[Pesquisa Binária]] é diferente. Se a lista tem 100 itens, precisa-se de, no máximo, sete tentativas. Se tem 4 bilhões, precisa-se de, no máximo, 32 tentativas. Poderoso, não? A pesquisa binária é executada com **tempo logarítmico**. *O(log n)*

*O(n log n)* Exemplo: um algoritmo rápido de ordenação, como a ordenação [[Quick Sort]].

*O(n^2)* Exemplo: um algoritmo lento de ordenação, como a [[Selection Sort]].

*O(n!)* Exemplo: um algoritmo bastante lento, como o do caixeiro-viajante[^1].

[^1]: O Problema do Caixeiro Viajante (PCV) é um problema que tenta determinar a menor rota para percorrer uma série de cidades (visitando uma única vez cada uma delas), retornando à cidade de origem. Calcular a menor rota entre um determinado numero de cidades é um exemplo de O(n!) pois confore o número de cidades aumenta o numero de operações para fazer o cálculo aumenta drasticamente, inviabilizando o cálculo para quando há muitas cidades.

![](https://miro.medium.com/max/1400/1*5ZLci3SuR0zM_QlZOADv8Q.jpeg)
