---
title: Strings JS
---

O tipo `String` em JavaScript é usado para representar textos, ou cadeias de caracteres. Tudo que estiver dentro das aspas (aspas simples `''` ou aspas duplas `""`) vai ser considerado texto. Além delas, será texto as Template string.

```js
const valor = 8;
const texto = `Valor: ${valor}`; //Uso se template string
```

É possível usar índices em strings => `string[1]`

## Métodos nativos
- `.toUpperCase()` `toLowerCase()`
	- convertem strings para caixa alta ou baixa
	- importante porque as linguagens diferenciam as letras maiúsculas de suas equivalentes minúsculas em uma comparações.
- `.length()` número de caracteres em uma string
- `.includes()`
	- o método retorna `true` se uma string contém uma string especificada, caso contrário, ele retorna `false` (é sensível a maiúsculas e minúsculas)
	- `string.includes(searchvalue, start)`
- `.replace()` o método pesquisa em uma string por um valor ou uma expressão regular. Retorna uma nova string com o(s) valor(es) substituído(s), sem alterar a string original.
``` js
let text = "Visit Microsoft!";
let result = text.replace("Microsoft", "W3Schools");
```
- `.charAt()` retorna o caractere em um índice especificado (posição) em uma string.
``` js
let text = "HELLO WORLD";
let letter = text.charAt(0); //H
```
- `.substr()` `.substring()` retorna uma parte da string
	- Forma de obter o último caractere de uma string
``` js
var ultima1 = palavra.substr(-1);
var ultima2 = palavra.charAt(palavra.length-1);
```
- `.indexOf()` pesquisa por caracteres (um ou mais), a pesquisa se dá a partir do **início** da string.
``` js
var palavra = "saladas";
var posicao1 = palavra.indexOf("a"); // retorna 1
var posicao2 = palavra.lastIndexOf("a"); // retorna 5
var posicao3 = palavra.indexOf("sal"); // retorna 0
var posicao4 = palavra.indexOf("e"); // retorna -1
```
- `.lastIndexOf()` pesquisa por caracteres (um ou mais), a pesquisa ocorre do final para o começo.
- `.split()` converte a string em elementos de vetor a cada ocorrência de um determinado caractere escolhido.
	- Pode ser usado em conjunto a outros métodos: aqui a entrada de texto é invertida `texto.split('').reverse().join('');`
``` js
var sabores = "calabresa, 4 queijos, atum, frango";
var partes = sabores.split(","); // = [calabresa, 4 queijos, atum, frango]
```
- `.match()` retorna uma correspondência entre uma string com uma expressão regular.
- `.replace()` método pesquisa uma string para um valor ou uma expressão regular e retorna uma nova string com o(s) valor(es) substituído(s) => não altera a string original
	- `string.replace(searchValue, newValue)`
- [ ] `.slice()`