---
title: Operadores JS
---

Podem ser:
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