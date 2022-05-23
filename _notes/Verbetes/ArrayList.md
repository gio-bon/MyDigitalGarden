---
title : ArrayList
---

Seu funcionamento pode ser pensado como uma Array crescente, que expande seu tamanho conforme a necessidade.
Esse tipo de array armazena os ponteiros (de forma contígua) com a localização dos valores primitivos armazenados em memória (não contíguos), e isso permite o acesso instantâneo aos dados.
Já vem com métodos prontos, bastando apenas os chamar, sem que você precise os criar manualmente: `Add`, `Remove`, `Get`, `Set`, `Clear`, `toArray` (converte a ArrayList em um Array).

Vantagens e desvantagens em relação à Arrays
- Possuem um tamanho dinâmico enquanto que arrays tem tamanho fixo
- Estão disponíveis métodos pré prontos enquanto que em arrays você deve criá-los
- Desvantagem de armazenar apenas objetos [^1] , enquanto que arrays armazena todos tipos de dados
- Desvantagem de requerer mais memória e manutenção em relação aos arrays

Assim as ArraysList funcionam melhor em programas mais interativos em que os dados serão bastante modificados. Já para arrays, performam melhor em tarefas menores, em que não estará interagindo ou alterando dados com frequência.

[^1]:Autoboxing: o arraylista armazena apenas objetos (não tipos primitivos), assim autoboxing é a conversão automática de um primitivo (que é passado para o método) para um objeto.