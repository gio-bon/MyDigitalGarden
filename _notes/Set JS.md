---
title: Set JS
---

Objetos Set são coleções de valores. Você pode iterar seus elementos em ordem de inserção. Um valor em um Set só pode ocorrer uma vez;  ele é único em uma coleção Set.

Relacionado a Arrays, com a diferença que possuem apenas valores únicos, de qualquer tipo e não possuem vários dos métodos disponíveis aos arrays, como Map, Filter e Reduce.

#### Vantagens de set em relação a arrays
- Checar se um elemento existe em uma coleção usando indexOf para arrays é lento.
- Objetos Set permitem que você exclua elementos por seu valor. Com um array você teria que unir baseado no índice do elemento.
- O valor NaN não pode ser encontrado com indexOf no array.
- Objetos Set armazenam valores únicos, você não tem que manter o controle de duplicidades manualmente por você mesmo.

``` js
var meuSet = new Set(); // criação

meuSet.add(1); // meuSet [1]
meuSet.add(5); // meuSet [1, 5]
meuSet.add(5); // 5 já foi adicionando, portanto, meuSet [1, 5]
meuSet.add("texto");
var o = {a: 1, b: 2};
meuSet.add(o);

meuSet.add({a: 1, b: 2}); //  o está referenciando outro objeto

meuSet.has(1); // true
meuSet.has(3); // false, 3 não foi adicionado ao set (Conjunto)
meuSet.has(5);              // true
meuSet.has(Math.sqrt(25));  // true
meuSet.has("Texto".toLowerCase()); // true
meuSet.has(o); // true

meuSet.size; // 5

meuSet.delete(5); // remove 5 do set
meuSet.has(5);    // false, 5 já foi removido

meuSet.size; // 4, nós simplesmente removemos um valor

console.log(meuSet) // Set { 1, 'texto', { a: 1, b: 2 }, { a: 1, b: 2 } } 
```