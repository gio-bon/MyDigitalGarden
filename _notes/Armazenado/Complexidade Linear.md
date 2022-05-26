---
title : Complexidade Linear
---

Considere um exemplo onde temos que inserir um elemento em um array. Teríamos que mover o elemento atual e todos os elementos subsequentes um lugar para a direita para liberar espaço para o novo elemento. O pior cenário seria se tivéssemos que inserir um elemento no início de um array, pois nesse caso todos os elementos do array devem ser movidos. Portanto, no pior caso, o tempo de inserção é diretamente proporcional ao número de elementos no array. Dizemos que o tempo de pior caso para a operação de inserção é linear no número de elementos no array. Para um algoritmo de tempo linear, se o tamanho do problema dobrar, o número de operações também dobra. Portanto, O(n) significa que o tempo de execução aumenta no mesmo ritmo da entrada.