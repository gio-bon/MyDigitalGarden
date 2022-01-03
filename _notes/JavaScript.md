---
title: JavaScript
---

## Comentários
É uma parte de código que não é interpretada pelo motor JavaScript. Pode ser utilizada, também, para colocar textos que ajudam a identificar o que está sendo feito naquele trecho de código.

``` js
  // Este é um comentário q vai explicar tudo abaixo
  
  /* Exemplo de comentário
      com várias linhas. */
```

## Variáveis
Podem ser consideradas como contêineres que permitem armazenar dados dentro elas. Em JS existem 3 tipos de variáveis
- `var`
	- De Escopo local e Escopo global
	- Podem ser redeclaradas, reatribuídas e tem o comportamento de hoisting
- `let`
	- Tem todos os JavaScript/Escopos, difere de var por ter o Escopo de bloco
	- Podem ser reatribuídas, ma NÃO ser redeclaradas NEM tem o comportamento de hoisting.
- `const`
	- Tem todos os JavaScript/Escopos
	- Cujo valor é fixo que não serão possíveis atribuir um novo valor
	- por padrão são declaradas na forma Upper Snake Case => `ESSA_E_CONSTANTE`

## Tipos de dados
- Primitivos:
	- Strings | Numbers | Booleans | Null e undefined
- Compostos
	- Arrays | Objetos

### Booleans
Representa uma entidade lógica e pode ter dois valores: verdadeiro `true` ou falso `false`, utilizado em comparações e estruturas de decisão.
- 
### Null e undefined
- `empty` atribuído o valor de 0 ou "".
- O tipo `Null` tem exatamente um valor: `null` (nulo, não existe).
- Uma variável que não tenha recebido nenhum valor específico, assume o valor `undefined` (indefinido).
- Outra forma de se obter `undefined` seria tentar pegar o retorno de uma função que não retorna nada, ou mesmo tentar acessar um parâmetro de função que não tenha recebido um argumento.

### Number
Number é usado para representar números, independente se for um número inteiro tipo `7` ou um número real como `32.4`.

Alguns métodos: `Math.floor()` e `Math.ceil()`

**BigInt** é um tipo de dado numérico que representa inteiros no formato de precisão arbitrária. Em outras linguagens de programação existem tipos numéricos diferentes, como por exemplo: Integers, Floats, Doubles ou Bignums.

### Strings
O tipo `String` em JavaScript é usado para representar textos, ou cadeias de caracteres. Tudo que estiver dentro das aspas (aspas simples `''` ou aspas duplas `""`) vai ser considerado texto. Além delas, será texto as Template string.

```js
const valor = 8;
const texto = `Valor: ${valor}`; //Uso se template string
```

É possível usar índices em strings => `string[1]`

#### Métodos nativos
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

### Arrays
É uma variável que contêm vários valores e é usados para armazenar um grupo de valores relacionados; podem armazenar quaisquer outro tipo diferentes de dados, inclusive arrays dentro de arrays.

É definido com colchetes `[ ]` => `const array_com_arrays = ["Heart", "Dev", [1, "Melhor Comunidade"]];`

#### Métodos nativos
- `.push()` **adiciona** um elemento ao **final** do vetor.
	- `cidades.push("São Lourenço")`
- `.unshift()` **adiciona** um elemento ao **início** do vetor e desloca os elementos existentes uma posição abaixo
	- `cidades.unshift("Porto Alegre")`
- `.pop()` **remove** o **último** elemento do vetor.
	- A variável recebe o conteúdo do elemento removido do vetor => `var retirada = cidades.pop()`
- `.shift()` **remove** o **primeiro** elemento do vetor e desloca os elementos existentes uma posição acima.
	- A variável recebe o conteúdo do elemento removido do vetor => `var retirada = cidades.shift()`
- `.splice()` para inserir / remover elementos no **meio** do vetor.
	- Remove 1 elemento a partir do índice 2, e insere "trumpet" =>
	  `removed = myFish.splice(2, 1, "trumpet");`
- `.length()` saber o número de elementos em um vetor, o que permite percorrê-la, fazer exclusões. > `cidades.length`
- `.indexOf()` vericação da existência ou não de um conteúdo do vetor.
	- `indexOf()`, a busca ocorre a partir do início do vetor > `idades.indexOf(6)`
	- `lastIndexOf()` a busca é do final até o seu início > `idades.lastIndexOf(6)`
	- Caso o conteúdo exista no vetor, o número do **índice** da primeira ocorrência desse conteúdo é retornado.
- `.includes()` retorna um valor booleano e é perfeito para lhe dizer se um elemento existe ou não em um array. Ele dá uma resposta simples true ou false.
	- `alligator.includes('thick scales', 1)` começa a pesquisa a partir do índice 1
- `.join()` convertem o conteúdo do vetor em uma string.
	- `cidades.join(" - ")` é frequentemente utilizado para consultar a lista; indica qual caractere vai separar os itens.
- `.toString()` também converte para strings, a diferença para `.join()` é que pode ser usado não apenas para vetores, mas também pra outros tipos de objetos e uma *vírgula* é inserida entre os elementos. >`cidades.toString()`
- `.sort()` `.reverse()` para classicar os itens em determinada ordem.
	- `lista.sort()` em ordem alfabética crescente
	- `lista.reverse()` inverte a ordem dos elementos de um vetor
	- Como ordenar números em uma lista.
``` js
//para ordenar números
const points = [40, 100, 1, 5, 25, 10];  
points.sort(function(a, b){return a - b});
```
- `.slice()` para criar uma cópia de um vetor original.
	- Apartir do método `slice` > esse método obtém um conjunto de elementos de um outro vetor, sem parâmetros, ele obtém uma cópia com todos os elementos do vetor original.  > `var copia = criancas.slice();`
- `.join()` junta todos os elementos de um array em uma única string.
``` js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let text = fruits.join(" and "); 
// Banana and Orange and Apple and Mango
```

- [ ] [Curso de JavaScript #11 - map, filter e reduce \(2020\) - YouTube](https://www.youtube.com/watch?v=D\_MExaVe95w&feature=youtu.be)
- [ ] `.map()` é utilizado geralmente quando você deseja percorrer um array e fazer uma alteração em cada elemento. E como consequência o método map gerar um array novo.
	- [Método JavaScript Array map ()](https://www.w3schools.com/jsref/jsref_map.asp)
- [ ] `.filter()` é usado para filtrar os itens de um array e apenas devolver aqueles que satisfazem a condição passada na função.
	- [JavaScript Array filter() Method](https://www.w3schools.com/jsref/jsref_filter.asp)
-  [ ] `.reduce()` é usado para reduzir o array para um único valor.
	- [JavaScript Array reduce() Method](https://www.w3schools.com/jsref/jsref_reduce.asp)
- [ ]  `.find()`
- [ ]  `.filter()`

#### Destructuring
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

#### Spread
Transforma um array-js em diversos parâmetros para uma função:
- **array => parâmetros**

``` js
const pessoas = ['Pedro', 'Maria'];
const todasAsPessoas = ['Marcus', 'Tiago', ...pessoas];

console.log(todasAsPessoas);
//[ 'Marcus', 'Tiago', 'Pedro', 'Maria' ]
```

#### Rest
Nos permite transformar um número indeterminado de parâmetros em um array-js
- **parâmetros => array**

``` js
function listagem (primeiro, segundo, ...outros) {
console.log(`Na lista estão: ${primeiro}, ${segundo}. Os demais são: ${outros.join(', ')}.`)
}
listagem('Pedro', 'Maria', 'João', 'Marcus');
//Na lista estão: Pedro, Maria. Os demais são: João, Marcus.
```

### Objetos
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

#### Propriedades
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

#### Métodos
São funções dentro de objetos.
Métodos nativos de objetos:
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

## Operadores
Aritméticos tomam valores numéricos como seus operandos e retornam um único valor numérico.

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

Operadores de atribuição são capazes de atribuir valores ao operando da esquerda baseado no operando da direita.
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

Incremento e decremento: acrescenta `++` ou decrescenta `--` um no dado tratado.
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

Operadores de comparação retornam um valor lógico se a comparação é verdadeira.
- `==` igual a
- `===` estrito (compara o tipo)
- `!=` diferente de
- `!==` estrito (compara o tipo)
- `>` `>=` menor
- `<` `<=` maior

### Lógicos
- AND `&&`
	- `var1 && var2`
- OR `||`
	- `var1 || var2`
- NOT `!`
	- `!var1`

O operador de negação unária precede seu operando e o nega.

``` javascript
let numero = 1;
console.log(numero); // 1
console.log(-numero); // -1
```

O `+` antes de uma variável, é a forma mais rápida e a forma preferida de converter alguma coisa em um número, porque ele não realiza nenhuma outra operação no número.
``` javascript
console.log(+3); // 3
console.log(+"3"); // 3
console.log(+true); // 1
console.log(+false); // 0
console.log(+null); // 0
```

## Condicionais
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

### Operador ternário
``` javascript
condicao ? valor1 : valor2;
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

## Repetição

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
Funciona para objetos iterativos (iteráveis), como array-js e strings-js e não com objeto-js

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
Percorre cada elemento de um array-js executando uma função que é passada como parâmetro

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

## Funções
É um bloco de códigos, que conseguimos utilizar sempre que chamarmos em qualquer parte da nossa aplicação, para realizar uma ação (permite a reutilização de código).
Uma função é definida pela palavra reservada `function`, seguida por um *nome* e então os parenteses `()`. Dentro dos parênteses, você insere os Parâmetros que são dados que serão processados pela função.

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

Atribuindo a uma variável

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
[Arrow Functions — Declaração, funcionamento, escopos e o valor de this by Raphael Lima - Medium](https://medium.com/@raphalima8/arrow-functions-declara%C3%A7%C3%A3o-funcionamento-escopos-e-o-valor-de-this-9cb6449bca31)

## Escopos
Escopo é a acessibilidade de objetos, variáveis e funções em diferentes partes do código. Em outras palavras, o escopo é quem determina quais são os dados que podem ser acessados em uma determinada parte do código.

### Local
Tudo que é declarado dentro de uma função.

### Global
Escopo global é tudo o que for declarado, criado fora de blocos `{ }` e de funções, por conta disso toda a nossa aplicação tem acesso a eles.

### De bloco
Um bloco é o que está dentro de `{ }`, assim escopo de bloco é que tudo o que está dentro de um bloco não é acessível fora dele.

No JS em especifico até o ES2016 (ECMAScript2016), tínhamos um grande problema ao declarar variáveis usando `var` dentro de blocos de instrução (IF, FOR, WHILE, etc...) pois esses blocos não criam o seu próprio escopo, o que fazia com que todas as variáveis declaradas com `var` dentro dele se tornassem globais. Por conta disso evitamos ao máximo o uso da `var`, pois a `let` nasceu dessa necessidade de podermos declarar variáveis com escopo local dentro de blocos de instrução

## Coleções
### Map
ECMAScript 6 apresenta uma nova estrutura de dados para mapear valores para valores. Um objeto Map é um simples mapa de chave/valor que pode ter seus elementos iterados por ordem de inserção.

É parecido com um objetos (tem a estrutura chave: valor), mas tem características próprias.

#### Diferenças em relação a objetos
- As chaves de um Objeto são Strings, onde elas podem ser de qualquer tipo para um Map.
- Você pode obter o tamanho de um Map facilmente enquanto que para um Object, você tem que obter manualmente o seu tamanho.
- A iteração de mapas é por ordem de inserção dos elementos.
- Um Object tem um protótipo, então existem chaves padrão no mapa. (este pode ser ignorado usando map = Object.create(null)).
- Estes dois tipos podem ajudar você a decidir se usa um Map ou um Object:
	- Use mapas sobre objetos quando as chaves forem desconhecidas até a execução,  e quando todas as chaves são do mesmo tipo e todos valores são do mesmo tipo.
	- Use mapas caso haja a necessidade de armazenar valores primitivos como chaves, porque objetos tratam cada chave como uma string ou um valor numérico, valor booleano ou qualquer outro valor primitivo.
	- Use objetos quando há uma lógica que opera em elementos individuais.

A maneira correta para armazenar dados dentro do Map é através do `set(key, value)`

``` js
const map1 = new Map(); //criação
//setando
map1.set('a', 1); 
map1.set('b', 2);
map1.set('c', 3);

console.log(map1.get('a'));
// expected output: 1

map1.set('a', 97); //alternado

console.log(map1.size);  //tamanho (lenght)
// expected output: 3

map1.delete('b'); //deletando

console.log(map1.size);  //tamanho (lenght)
// expected output: 2
```

### Set
Objetos Set são coleções de valores. Você pode iterar seus elementos em ordem de inserção. Um valor em um Set só pode ocorrer uma vez;  ele é único em uma coleção Set.

Relacionado a Arrays, com a diferença que possuem apenas valores únicos, de qualquer tipo e não possuem vários dos métodos disponíveis aos arrays, como Map, Filter e Reduce.

#### Vantagens de set em relação a arrays
- Checar se um elemento existe em uma coleção usando indexOf para arrays é lento.
- Objetos Set permitem que você exclua elementos por seu valor. Com um array você teria que unir baseado no índice do elemento.
- O valor NaN não pode ser encontrado com indexOf no array.
- Objetos Set armazenam valores únicos, você não tem que manter o controle de duplicidades manualmente por você mesmo.

``` js
var meuSet = new Set(); // criação

meuSet.add(1); // meuSet [1]
meuSet.add(5); // meuSet [1, 5]
meuSet.add(5); // 5 já foi adicionando, portanto, meuSet [1, 5]
meuSet.add("texto");
var o = {a: 1, b: 2};
meuSet.add(o);

meuSet.add({a: 1, b: 2}); //  o está referenciando outro objeto

meuSet.has(1); // true
meuSet.has(3); // false, 3 não foi adicionado ao set (Conjunto)
meuSet.has(5);              // true
meuSet.has(Math.sqrt(25));  // true
meuSet.has("Texto".toLowerCase()); // true
meuSet.has(o); // true

meuSet.size; // 5

meuSet.delete(5); // remove 5 do set
meuSet.has(5);    // false, 5 já foi removido

meuSet.size; // 4, nós simplesmente removemos um valor

console.log(meuSet) // Set { 1, 'texto', { a: 1, b: 2 }, { a: 1, b: 2 } } 
```

## This
É uma referência contextual, que pode mudar de acordo de onde no código que ele é chamado.
- Dentro de objetos, o `this` será o dono do objeto, com suas propriedades.
- Sozinho e em funções, o `this` vai se referir ao objeto global (em navegadores é o objeto `window`)
- Em eventos, o `this` será o próprio elemento que recebeu o evento.

[Entendendo This, Bind, Call e Apply no JavaScript by Maicon Silva](https://www.maiconsilva.com/entendendo-this-bind-call-e-apply-no-javascript/)

### `call` e `apply`
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

### `bind`
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

## Tratamento de erros
Ao executar o código JavaScript, podem ocorrer erros diferentes. Os erros podem ser erros de codificação cometidos pelo programador, erros devido a entrada incorreta e outras coisas imprevisíveis.

O Ecmascript Error é um tipo de erro em tempo de execução, já o DOM Exception é um erro referente a DOM.
- A composição do Ecmascript Error é => mensagem, nome, linha e call stack

### `try` `catch` `finally`
- `try` permite definir um bloco de código a ser testado quanto a erros enquanto ele está sendo executado.
- `catch` permite definir um bloco de código a ser executado, se ocorrer um erro no bloco `try`.
- `finally` permite executar o código, após tentar e capturar, independentemente do resultado.

``` js
  try {
	tryCode - Block of code to try
	//Requeridos. Bloco de código a ser testado para erros enquanto está sendo executado
  }
  catch(err) { //Especifica uma variável local que se refere ao erro. 
	catchCode - Block of code to handle errors 
	//Opcional. Bloco de código a ser executado, caso ocorra um erro no bloco try. Se nenhum erro ocorrer, este bloco de código nunca é executado
  }
  finally {
	finallyCode - Block of code to be executed regardless of the try / catch result
	//Opcional. Bloco de código a ser executado independentemente do resultado de tentativa / captura
  }
```

### `thow`
A instrução `throw` permite que você crie um erro personalizado.

``` js
if (typeof string != 'string') throw "string inválida";
```

### `error`
- [ ] TODO
``` js
//new Error(message, fileName, lineNumber)
let meuError = new Error('Muitos erros meou!');
throw meuError;
```

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

Veja: [[JavaScript Assíncrono]]

---

**Roteiro**:
- [x] Síntaxe e construtores básicos
- [x] Aprender a manipular o [[DOM]]
- [ ] Aprender [[Fetch API]] / Ajax (XHR)
- [ ] ES6+ e JavaScript Modular

Entender os conceitos:
	- [ ] Hoisting
	- [ ] Event Bubbling
	- [x] Scope (escopos)
	- [ ] Prototype
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