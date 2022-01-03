---
title: ES6
---

O [TC39](http://www.ecma-international.org/memento/TC39.htm) é o comitê responsável pelas atualizações (evolução) da linguagem, e faz o _release_ anual (o ES6 é um desses releases). O processo geral para fazer alterações nas especificações da linguagem é feito por Stages.

Fluxo de propostas: 
Stage O: strawman
Stage 1: proposal
Stage 2: draft
Stage 3: candidate
Stage 4: finished

[tc39/proposals: Tracking ECMAScript Proposals](https://github.com/tc39/proposals)

O TC39 focou em alguns objetivos no desenvolvimento do ES6:
-   Ser uma linguagem melhor para construir aplicações complexas
-   Resolver problemas antigos do JavaScript
-   Facilidade no desenvolvimento de _libraries_

Como muitas dessas novas features das releases não são suportadas pelas navegadors, é preciso de algo que converta o JS escrito com o ES6 para algo que esses navegadores suportem. O [Babel](https://babeljs.io/) transforma o código de ES6 para ES5 (versão que a maioria dos browsers dá suporte hoje). Esse processo é chamado de transpilação.

Novos recursos no ES6: 
- [x] Inclusão de `let` e `const`
- [x] Arrow Functions
- [x] For/of
- [x] [[Map JS]]
- [x] [[Set JS]]
- [ ] Classes
- [ ] Promises
- [x] Symbol
- [x] Default Parameters
- [ ] Function Rest Parameter [[Rest JS]]
- [ ] String.includes()
- [ ] String.startsWith()
- [ ] String.endsWith()
- [ ] Array.from()
- [ ] Array keys()
- [ ] Array find()
- [ ] Array findIndex()
- [ ] New Math Methods
- [ ] New Number Properties
- [ ] New Number Methods
- [ ] New Global Methods
- [ ] Iterables Object.entries
- [ ] JavaScript Modules

---

https://www.w3schools.com/js/js_es6.asp