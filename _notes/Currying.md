---
title: Currying
---

**Currying** é o processo de transformar uma função que espera vários argumentos em uma função que espera um único argumento e retorna outra função _curried_. Por exemplo, uma função que recebe três argumentos, ao sofrer currying, resulta em uma função que recebe um argumento e retorna uma função que recebe um argumento, que por sua vez retorna uma função que recebe um argumento e retorna o resultado da função original.

```js
function soma(a) {
	return function(b) 
	return a + b; 
	} 
} 

const soma2 = soma(2); 

console.log(soma2(2));
console.log(soma2(3));
console.log(soma2(4));
console.log(soma2(5));
```

- [Currying](https://javascript.info/currying-partials)
- [JavaScript: Currying](https://rodrigorgs.github.io/aulas/mata56/aula14-currying)