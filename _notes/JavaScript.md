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

## Operadores
Podem ser 
- operadores **unários** (bastando para um elemento), 
- operadores **binários** (bastando para dois elemento)
- operador **ternário**, no formato `condicao ? valor1 : valor2;` (dependendo da condição, se verdadeiro, a variável recebe o valor1; se falso a variável recebe o valor2)

**Aritméticos** (binário) tomam valores numéricos como seus operandos e retornam um único valor numérico.

``` javascript
let foo = 2;
const bar = 3;
foo + bar; 
foo - bar;
foo * bar;
foo / bar;
foo ** bar;
foo % bar;
```

O operador de **negação** (unário) precede seu operando e o nega.

``` javascript
let numero = 1;
console.log(numero); // 1
console.log(-numero); // -1
```

O `+` (unário) antes de uma variável, é a forma mais rápida e a forma preferida de converter alguma coisa em um número, porque ele não realiza nenhuma outra operação no número.

``` javascript
console.log(+3); // 3
console.log(+"3"); // 3
console.log(+true); // 1
console.log(+false); // 0
console.log(+null); // 0
```

Operadores de **atribuição** (binário) são capazes de atribuir valores ao operando da esquerda baseado no operando da direita.

``` javascript
let foo = 2;
const bar = 3;
foo += bar;  // foo = foo + bar
foo -= bar;
foo *= bar;
foo /= bar;
foo **= bar;
foo %= bar;
```

**Incremento e decremento** (unário): acrescenta `++` ou decrescenta `--` um no dado tratado.
Se usado depois da variável, ele incrementa o valor depois retorna.

``` javascript
let numero = 1;
console.log(numero); // 1
console.log(numero++); // 1
console.log(numero); // 2
```

Se usado antes da variável, ele retorna o valor depois incrementa.

``` javascript
let numero = 1;
console.log(numero); // 1
console.log(++numero); // 2
console.log(numero); // 2
```

Operadores de **comparação** (binário) retornam um valor lógico se a comparação é verdadeira.
- `==` igual a
- `===` estrito (compara o tipo)
- `!=` diferente de
- `!==` estrito (compara o tipo)
- `>` `>=` menor
- `<` `<=` maior

Operadores **lógicos** (binário):
- com **e** ou **and**
	- `&&` em `var1 && var2`, se ambas variáveis forem verdadeiras, retorna `true`
- com **ou** ou **or**
	- `||` em `var1 || var2`, se pelo menos uma variável for verdadeiras, retorna `true`
- com **not** (unário)
	-  `!` em `!var1` negará o valor lógico de `var1`

- [[Spread JS]]
- [[Destructuring JS]]
- [[Rest JS]]

## Estruturas Condicionais
### `else` `else if` `else`

``` javascript
if (condicao) {
// código para executar caso a condição seja verdadeira
} else if (outraCondicao) {
// senão, executar este código caso outra condição seja verdadeira
} else {
// senão, executar este código
}
```

### `switch` `case`
- Bom para comparações de muitos valores
- Fará comparações de tipo e valor (`===`)
- Sempre precisará de um `default`
- 
``` javascript
  switch (expression) {
  case choice1:
	// código para executar
	break;
	case choice2:
	// código para executar
	break;
  // podem ser incluídos quantos casos precisar.
	default:
  // se não for nenhum caso, executa este caso
  }
```

## Estruturas de Repetição

### For

``` javascript
for ([expressaoInicial]; [condicao]; [incremento]) {
// ações a serem repetidas
}
```

Percorrendo arrays

``` js
for(let i = 0; i < lista.length; i++){
	  //fazer algo com lista[i]
  }
```

#### For ... in
Percorre as propriedades enumeradas (índices ou chaves), portanto podendo ser usado em objetos e arrays

``` javascript
let arrials = [10, 20, 30, 40, 50, 60];
let objectials = {num1: 1, num2: 2, num3: 3, num4: 4, num5: 5, num5: 6}

for(let prop in arrials){
console.log(prop); //0 1 2 3 4 5 => percorre os índices
}

for(let prop in objectials){
console.log(prop); //num1 num2 num3 num4 num5 => percorre as chaves
}
```

Para que passe a acessar os valores em sí, deve-se usar `prop[arrials]` ou  `prop[objectials]` nos consoles log

#### For ... of
Funciona para objetos iterativos (iteráveis), como arrays e strings e não com objetos

``` javascript
let arrials = [10, 20, 30, 40, 50, 60];
let stringola = "Soy una stringola"

for(let prop of arrials){
console.log(prop); // 10 20 30 40 50 60
}

for(let prop of stringola){
console.log(prop); //percorre cada caracter da string
}
```

#### forEach
Percorre cada elemento de um array executando uma função que é passada como parâmetro

``` js
  let arrials = [10, 20, 30];
  let sum1 = 0, sum2 = 0;

  function multiply2X(currentValue, index, arr, thisValue){
	console.log(`${currentValue} -> ${index} => ${arr}`);
	arr[index] *= 2;
	sum1 += arr[index];
	sum2 += currentValue;
  }

  arrials.forEach(multiply2X);
  /*	10 -> 0 => 10,20,30
	20 -> 1 => 20,20,30
	30 -> 2 => 20,40,30  */
  console.log(arrials); //[ 20, 40, 60 ]
  console.log(sum1, sum2); //120 60
```

[Qual a diferença entre for in, for of e forEach no JavaScript? by João Victor Pereira Santos - Medium](https://medium.com/@joaovictorpsantos/qual-a-diferen%C3%A7a-entre-for-in-for-of-e-foreach-no-javascript-7af6f6a56eea)

#### While
Executa instruções até que a condição se torne falsa

``` javascript
while (condicao) {
  // ações a serem repetidas
}
```

#### Do .... while
Executa instruções até que a condição se torne falsa, executa pelo menos uma vez
``` javascript
do {
// ações a serem repetidas
} while (condicao);
```

#### `break` e `continue`
São dois comandos especiais são utilizados nas estruturas de repetição.
- O `break` sai do laço de repetição, enquanto que o `continue` retorna ao início do laço. Estes comandos nos **auxiliam no controle de execução dos comandos do loop**.
- Os comandos `break` e `continue` podem ser utilizados nas três estruturas de repetição disponíveis: for, while ou do... while.
- Caso o comando continue seja executado em um laço for, o incremento ou decremento da variável de controle ocorre normalmente, como se o laço tivesse sido executado até o seu final.

#### Contadores e acumuladores
O uso de contadores e acumuladores em um programa permite a exibição de contagens e totalizações. Essas operações são realizadas sobre os dados manipulados pelo programa. Os contadores ou acumuladores possuem duas características principais:
- devem receber uma atribuição inicial (geralmente zero).
- devem receber ela mesma mais algum valor.

A diferença entre os contadores e os acumuladores é que o contador recebe ele mesmo mais 1 (ou algum valor constante), enquanto o acumulador recebe ele mesmo mais uma variável.
- contador => `i++` ou `i = i + 1`
- acumulador => `var = var + outraVar`

**Flags**: nesse código, como fazer com que ele informe o usuário que no array não há ninguém maior de idade?

``` js
  var idades = [12, 26, 15, 17, 14];
  for (var i = 0; i < idades.length; i++) {
	if (idades[i] >= 18) {
		lert(idades[i]);
	}
  }
```

A solução para esse cenário é utilizar uma variável de controle. Caso a condição dentro do laço seja verdadeira, modica-se o valor da variável. Após o laço, deve-se verificar, então, se a variável mantém o valor inicial. Isso significa que a condição testada no laço não ocorreu e que, portanto, a mensagem indicativa deve ser exibida.

``` js
var maiores = false;
for (var i = 0; i < idades.length; i++) {
	if (idades[i] >= 18) {
	alert(idades[i]);
	maiores = true;
	}
}
if (!maiores) {
	alert("Não há idades maiores que 18 na lista");
}
```

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