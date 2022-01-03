---
title: Rest JS
---

Nos permite transformar um número indeterminado de parâmetros em um array
- **parâmetros => array**

``` js
function listagem (primeiro, segundo, ...outros) {
console.log(`Na lista estão: ${primeiro}, ${segundo}. Os demais são: ${outros.join(', ')}.`)
}
listagem('Pedro', 'Maria', 'João', 'Marcus');
//Na lista estão: Pedro, Maria. Os demais são: João, Marcus.
```