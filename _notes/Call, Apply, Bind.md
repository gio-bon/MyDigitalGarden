---
title: Call, Apply, Bind
---

## `call` e `apply`
Ambos fazem a mesma coisa. Diferença é na forma como são passados os argumentos para dentro dos métodos. Com o `apply` é possível passar um arry de argumentos => [JavaScript Function Apply()](https://www.w3schools.com/js/js_function_apply.asp)

- `call` -> aceita lista de argumentos
- `apply` -> aceita array de argumentos

``` js
const obj1 = { nome: 'Maria', mostraThis: function () {
console.log(this.nome);
}}
const obj2 = { nome: 'João'};

obj1.mostraThis.call(obj2);
obj1.mostraThis(); //João
```

``` js
let pessoa1 = {nome: 'Pastoso', idade: 18}
let pessoa2 = {nome: 'Chuvoso', idade: 33, calculaIdades: function (anos) {return `Daqui a ${anos} anos, ${this.nome} terá ${this.idade + anos} anos de idade.`;}}

let callPessoa1 = pessoa2.calculaIdades.call(pessoa1, 2); //call chamando pessoa 1
console.log(callPessoa1);
// Daqui a 2 anos, Pastoso terá 20 anos de idade.
```

## `bind`
O principal objetivo do método bind é alterar o contexto `this` de uma função independente de onde a mesma esteja sendo chamada.

Meio que transforma a função em um método do objeto à qual fica ligada.

``` js
  function thidBindExemplo(){
	console.log(this.nome);
	console.log(this.sobrenome);
  }

  const obj = { nome: 'Bereta', sobrenome: 'Gazola' }
  thidBindExemplo = thidBindExemplo.bind(obj); //sem essa linha o this apontaria para "window" (em navegadores)
  thidBindExemplo(); //Bereta Gazola
```