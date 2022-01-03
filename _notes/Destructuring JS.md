---
title: Destructuring JS
---

Permite extrair de um array ou objetos valores e transformar em uma variável ou constante
``` js
let arrayiz = [1, 10, 100, 1000]
const [itemA, itemB, ...nosotros] = arrayiz;

console.log(itemA, itemB, nosotros);
//			1 		10 	  [ 100, 1000 ]
```

``` js
const usuario = { nome: "Rolando", idade: 18, temFilhos: true }
const {nome, idade, temFilhos} = usuario;

console.log(nome, idade, temFilhos);
//Rolando 18 true
```