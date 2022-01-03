---
title: Objetos JS
---

Os objetos são muito semelhantes aos arrays pois são variáveis que podem conter vários valores, a diferença é que objetos têm um conjunto de `chave/propriedade: valor` que ajuda a dar mais significado às informações armazenadas neles. São criados com chaves `{}` e separados por `,`

Podemos imaginar um objeto como sendo uma gaveta, onde nessa gaveta existem pastas. Cada dado é armazenado em seu arquivo pela chave.

  ``` js
const professor = {
nome:    "He4rt",
nota:    10,              // avaliação do professor
classes: [1, 2, 3, 4, 5]  // ids das classes que leciona.
};
  ```

Os `valores` podem ser de qualquer tipo de dados.

## Propriedades
Adicionar e remover propriedades com `.`, `[]` e `delete`

``` javascript
let he4rt = {
  comunidade: "Ativa",
  devs: "Incríveis"
};

he4rt.key = "adicionada"
he4rt["nome"] = "Vitor"

console.log(he4rt) 
// {comunidade: "Ativa", 
//devs: "Incríveis", 
//key: "adicionada"
//nome: "Vitor"}

//para remover uma chave
delete he4rt.devs;
```
Acesso a propriedades

``` javascript
let helloWorld = {
	hello: "Hello ",
	world: "World"
}
console.log(helloWorld.hello + helloWorld.world) // Hello World
```

## Métodos
São funções dentro de objetos.

### Métodos nativos
- `Object.keys()` `Object.values` retornam chaves e valores de objetos

``` js
let objecto = {
name: "Neo",
lastname: "Anderson"
} 
let chave = Object.values(objecto);
let valor = Object.keys(objecto);
console.log(chave, valor);
//[ 'Neo', 'Anderson' ] [ 'name', 'lastname' ]
```

- `Object.entries()` retorna um array de arrays com as chaves e valores
- `Object.assign()` faz o merge de valores de propriedades
- `Object.freeze()` impede alterações em um objeto, depois de setado
- `Object.seal()` impede deletar e criar propriedades em objetos, parecido com freeze, porém mais permissivo.