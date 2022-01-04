---
title: Estruturas de Repetição JS
---

## For

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

### For ... in
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

### For ... of
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

### forEach
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

## While
Executa instruções até que a condição se torne falsa

``` javascript
while (condicao) {
  // ações a serem repetidas
}
```

### Do .... while
Executa instruções até que a condição se torne falsa, executa pelo menos uma vez
``` javascript
do {
// ações a serem repetidas
} while (condicao);
```

## `break` e `continue`
São dois comandos especiais são utilizados nas estruturas de repetição.
- O `break` sai do laço de repetição, enquanto que o `continue` retorna ao início do laço. Estes comandos nos **auxiliam no controle de execução dos comandos do loop**.
- Os comandos `break` e `continue` podem ser utilizados nas três estruturas de repetição disponíveis: for, while ou do... while.
- Caso o comando continue seja executado em um laço for, o incremento ou decremento da variável de controle ocorre normalmente, como se o laço tivesse sido executado até o seu final.

## Contadores e acumuladores
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