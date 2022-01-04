---
title: JavaScript
---

- O nome oficial da linguagem é ECMAScript (ES é uma abreviação).
- É uma linguagem interpretada (vs. compilada), de tipagem fraca (vs. forte) e dinâmica (vs stática).
- [TC39](http://www.ecma-international.org/memento/TC39.htm) é o comitê responsável pelas atualizações da linguagem, e faz o _release_ anual ([[ES6]] é um desses releases)

## Comentários
É uma parte de código que não é interpretada pelo motor JavaScript. Pode ser utilizada, também, para colocar textos que ajudam a identificar o que está sendo feito naquele trecho de código.

``` js
  // Este é um comentário q vai explicar tudo abaixo
  
  /* Exemplo de comentário
      com várias linhas. */
```

## Variáveis
Podem ser consideradas como contêineres que permitem armazenar dados dentro elas. Em JS existem 3 tipos de variáveis:
- `var`
	- De escopo local e escopo global
	- Podem ser redeclaradas, reatribuídas e tem o comportamento de hoisting
- `let`
	- Tem todos os 3 escopos, difere de var por ter o escopo de bloco
	- Podem ser reatribuídas, ma NÃO ser redeclaradas NEM tem o comportamento de hoisting.
- `const`
	- Tem todos os 3 escopos
	- Cujo valor é fixo que não serão possíveis atribuir um novo valor
	- por padrão são declaradas na forma Upper Snake Case => `ESSA_E_CONSTANTE`
	- é possível criar uma contante de array ou objeto, e, por mais que não se possá alterá-las, é possível alterar os valores desses objetos ou arrays (pois são passados por referência à uma localização de memória). 

Veja [[Escopo Léxico JS]] e [[Hoisting JS]]

- [Javascript \(ES6+\): entendendo var, let e const by Stéphano Wallace - Medium](https://medium.com/@stephanowallace/javascript-es6-entendendo-var-let-e-const-7a839e369810)

## Tipos de dados
O tipo de uma variável é definido em sua atribuição, e podem ser:
- Primitivos:
	- Strings | Numbers | Booleans | Null e undefined | Symbol
- Compostos: 
	- Arrays | Object | Function
		- são variáveis passadas por referência (apontando a localização na memória).

O tipo [[Strings JS|String]] em JavaScript é usado para representar textos, ou cadeias de caracteres. Tudo que estiver dentro das aspas (aspas simples `''` ou aspas duplas `""`) vai ser considerado texto.

**Booleans** representa uma entidade lógica e pode ter dois valores: verdadeiro `true` ou falso `false`, utilizado em comparações e estruturas de decisão.
- Veja [[Falsy e Truthy no JS]]

**Numbers** são usados para representar números, independente se for um número inteiro tipo `7` ou um número real como `32.4`.

Alguns métodos de numbers: 
- [ ] `.toFixed()`
- [ ] `parseFloat()`
- [ ] `parseInt()`
- [ ] `Math.floor()` e `Math.ceil()`

- **BigInt** é um tipo de dado numérico que representa inteiros no formato de precisão arbitrária. Em outras linguagens de programação existem tipos numéricos diferentes, como por exemplo: Integers, Floats, Doubles ou Bignums.

O tipo **Null** tem exatamente um valor: `null` (nulo, não existe).

Uma variável que não tenha recebido nenhum valor específico, assume o valor **Undefined** (indefinido).
- Outra forma de se obter Undefined seria tentar pegar o retorno de uma função que não retorna nada, ou mesmo tentar acessar um parâmetro de função que não tenha recebido um argumento.

[[Arrays JS|Arrays]] é um tipo de dados em variáveis que é usado para armazenar um grupo de valores relacionados e dentro dele pode armazenar quaisquer outro tipo diferentes de dados, inclusive arrays dentro de arrays.
- É criado com `[]` > `const array_com_arrays = ["Heart", "Dev", [1, "Melhor Comunidade"]];`

[[Objetos JS|Objetos]] são criados com chaves `{}`, possuindo conjuntos de propriedades em formato de `chave/propriedade: valor`, separados por `,`. Tamém podem possuír métodos dentro deles, que são espécies de funções dentro dos objetos, podendo alterar suas propriedades.

- [[Operadores JS]]
- [[Spread JS]]
- [[Destructuring JS]]
- [[Rest JS]]

- [[Estruturas Condicionais JS]]
- [[Estruturas de Repetição JS]]

[[Funções JS|Função]] é um bloco de código que faz coisas, que pode ser chamado em qualquer local do programa. 
- tem parâmetros dentro das `()` (valores que serão usados dentro do processamento da função)
	- é possível usar parâmetros padrões, quando não forem passados
- pode ter um retorno com `return` (retornando um valor para quem a chamar, inclusive podendo ser usado como parâmetro de outras funções) ou não.

Tipos de funções no JS:
- Funções normais

``` javascript
//declarando a função
function nome_funcao(param1, param2) {
	// código a ser executado
	return result;
}
nome_funcao(param1, param2); //invocando a função
```

- Funções anônimas

```js
var square = function(numero) {return numero * numero};
var x = square(4) //x recebe o valor 16
```

- Funções autoinvocáveis

``` js
  ( 
	function(a, b){  //pode ou não ter um nome
		return a + b;
	}
  )(1, 2);
```

- Arrow function

``` js
let myFunction = (a, b) => a * b;
```

- [[Map JS]]
- [[Set JS]]
- [[Tratamento de Erros JS]]

[JavaScript Errors Try Catch Throw](https://www.w3schools.com/js/js\_errors.asp)

## Date
As datas JavaScript são armazenadas internamente como um *valor numérico*. Assim, uma data também pode ser criada ou calculada apartir de um número **expresso em milissegundos**, a contar do dia 1 de janeiro de 1970.
- 86400000 é o número de milissegundos de um dia (1 dia = 24hor x 60min x 60seg x 1000mseg = 86400000)
- A variação do **mês** na linguagem JavaScript inicia em 0 e vai até 11. Para o dia e o ano, não há esse problema.

- Declarar uma variável que **recebe a data atual** um (objeto que recebe uma instância do objeto *Date*) > `var hoje = new Date()`
- Obtêm, retorna números, podendo ser feitos cálculos com os mesmos > `getDate()` `getMonth()` `getFullYear()`
- Setar (alterar) > `setDate()` `setMonth()` `setFullYear()`

## localStorage
Serve para salvar, recuperar e remover dados armazenados localmente no navegador. Pode-se acompanhar o conteúdo dessas variáveis nas opções do menu Ferramentas do desenvolvedor disponível no seu navegador (aplicativo > armazenamento local).
- Para **gravar** um conteúdo no LocalStorage > `localStorage.setItem("chave", valor)`
- Para **recuperar** o conteúdo no navegador > `localStorage.getItem("chave")`
- Para **excluir** os dados salvos pelo cliente em seu navegador > `localStorage.removeItem("chave")`

Veja: [[ES6]], [[JavaScript Assíncrono]]

Conceitos: [[Imutabilidade]]

---

**Roteiro**:
- [x] Síntaxe e construtores básicos
- [x] Aprender a manipular o [[DOM]]
- [ ] Aprender [[Fetch API]] / Ajax (XHR)
- [ ] [[ES6]] e JavaScript Modular

Entender os conceitos:
- [ ] Event Bubbling
- [ ] Shadow DOM
- [ ] strict mode

Aprenda as peculiaridades
	- Detalhes sobre tempo de execução, concorrência, modelo de memórias etc

Frameworks
- Vanilla javascript é o js puro, sem uso de frameworks.
- VueJS
- Angular
- React (biblioteca)
- JQuery

---

- [javascript4noobs: Este repositório tem como propósito fornecer uma iniciação na linguagem.](https://github.com/ThiagoDellaNoce/javascript4noobs) 
- [braziljs/eloquente-javascript: Tradução do livro Eloquent JavaScript - 2ª edição.](https://github.com/braziljs/eloquente-javascript)
- [The Modern JavaScript Tutorial](https://javascript.info/)
- [33 JavaScript concepts every developer should know.](https://github.com/leonardomso/33-js-concepts)
- [You-Dont-Know-JS](https://github.com/cezaraugusto/You-Dont-Know-JS)
- [airbnb/javascript: JavaScript Style Guide](https://github.com/airbnb/javascript)

---

- [10 Dicas para se Tornar Ninja em JavaScript! - DEV Community](https://dev.to/azure/10-dicas-para-se-tornar-ninja-em-javascript-1775)