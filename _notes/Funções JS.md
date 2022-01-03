---
title: Funções JS
---

É um bloco de códigos, que conseguimos utilizar sempre que chamarmos em qualquer parte da nossa aplicação, para realizar uma ação (permite a reutilização de código).
Uma função é definida pela palavra reservada `function`, seguida por um *nome* e então os parenteses `()`. Dentro dos parênteses, você insere os Parâmetros que são dados que serão processados pela função.

No JS as funções são objetos.

``` javascript
//declarando a função
function nome_funcao(param1, param2) {
	// código a ser executado
	return result;
}
nome_funcao(param1, param2); //invocando a função
```

Funções se tornam mais úteis se retornarem um valor, pois dessa forma o programa que chamou a função define o que deseja realizar com o conteúdo retornado. Para fazer uma função retornar um valor, utiliza-se o comando `return` seguido do conteúdo de retorno. Ao ser usado `return` ela interrompe a função e sai dela.

### Parâmetros
- `arguments` dentro de funções armazena todos os parâmetros ou argumentos passados a uma função.

``` js
function mostraArgs(){
	console.log(arguments);
	let soma = 0;
	for(let i = 0; i < arguments.length; i++){
	  soma += arguments[i];
}
	return console.log(soma);
}

mostraArgs(1, 2, 3, 4);
//`3: [Arguments] { '0': 1, '1': 2, '2': 3, '3': 4 }`
//`8: 10`
```

#### Parâmetro padrão

``` js
function Tester(nome, defeito = "idiota"){
console.log(`${nome} é um(a) ${defeito}!`);
}

Tester('Roberto') //Roberto é um(a) idiota!
Tester('Jéssica', 'baiana'); //Jéssica é um(a) baiana!
```

É comum a necessidade de passar um número indefinido de parâmetros para uma função, Array ou Objetos, nesses casos podemos utilizar os operadores rest e spread.

### Funções anônimas
São funções sem um nome específico e que podem ter seu valor atribuído a uma variável.

``` javascript
var fibonacci = function (num) {  //a funcao pode ou não ter um nome
if (num == 1 || num == 2) return 1;
else return fibonacci(num - 1) + fibonacci(num - 2);
};
console.log(fibonacci(10)); // 55
```

### Função autoinvocável (IIFE)
``` js
  ( 
	function(a, b){  //pode ou não ter um nome
		return a + b;
	}
  )(1, 2);
```

### Arrow Function
Uma expressão arrow function possui uma sintaxe mais curta, sendo menos verbosas.

``` js
let myFunction = (a, b) => a * b;
```

Com mais de uma linha

``` js
let hello = () => {
...
return "Hello World!";
}
```

Com uma linha, nem precisa do `return` e com apenas um parâmetro não é necessário os parênteses

``` js
let hello = nome => `Hello World ${nome}`;
```
- Restrições das arrow functions
	- Diferenças em relação ao this-js
	- Não existem os `arguments`
	- Não funciona com construtores

- [[Função First-class]]
- [[Currying]]

---

- [Funções - JavaScript | MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Functions)
- [Referência prática de funções anônimas em JavaScript](http://devfuria.com.br/javascript/funcoes-anonimas/)
- [ES6: arrow functions em 5 minutos - Blog | Raphael Fabeni](https://raphaelfabeni.com/es6-arrow-functions/)
- [Arrow Functions — Declaração, funcionamento, escopos e o valor de this by Raphael Lima - Medium](https://medium.com/@raphalima8/arrow-functions-declara%C3%A7%C3%A3o-funcionamento-escopos-e-o-valor-de-this-9cb6449bca31)
- [Arrow Functions vs. Functions em JavaScript - YouTube](https://www.youtube.com/watch?v=S5Mn0qQzJ-0)