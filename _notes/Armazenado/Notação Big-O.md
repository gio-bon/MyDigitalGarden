---
title : Notação Big-O
---

A Notação Big-O é a forma de julgar a velocidade e eficiência de diferentes estruturas de dados, e ajudam a definir quando usar (ou não) determinada estrutura.

Medimos a eficiência ou velocidade de uma estrutura de dados com base em quão bem ela pode realizar quatro tarefas básicas, como **acessar**, **pesquisar**, **inserir** ou **excluir** elementos em seus dados. Cada um desses critérios é modelado por uma equação que considera o tamanho da estrutura de dados em **números de elementos** e retorna o **número de operações** necessárias para serem executadas pelo computador para concluir essa tarefa. Essa métrica sempre é considerada **no pior cenário possível**. Ao medir essas quatro métricas, podemos obter uma boa compreensão em que uma estrutura de dados é boa ou ruim (em termos de eficiência).

### Complexidades
A notação Big-O é a linguagem usada para falar sobre quanto tempo o algoritmo leva para ser executado (**complexidade de tempo**) ou quanta memória é usada para executá-lo (**complexidade de espaço**).

![](https://miro.medium.com/max/1400/1*5ZLci3SuR0zM_QlZOADv8Q.jpeg)

- O(2^n) = Complexidade Exponencial
- O(n^2) = [[Complexidade Quadrática]]
- O(n) = [[Complexidade Linear]]
- O(log n) = [[Complexidade Logarítmica]]
- O(1) = [[Complexidade Constante]]