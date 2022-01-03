---
title: Arrays JS
---

### Arrays
É um tipo de dados em variáveis que é usado para armazenar um grupo de valores relacionados e dentro dele pode armazenar quaisquer outro tipo diferentes de dados, inclusive arrays dentro de arrays.
- É definido com colchetes `[ ]` => `const array_com_arrays = ["Heart", "Dev", [1, "Melhor Comunidade"]];`
- No JS os arrays são objetos.

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

- [ ] `.map()` é utilizado geralmente quando você deseja percorrer um array e fazer uma alteração em cada elemento. E como consequência o método map gerar um array novo.
	- [Método JavaScript Array map ()](https://www.w3schools.com/jsref/jsref_map.asp)
- [ ] `.filter()` é usado para filtrar os itens de um array e apenas devolver aqueles que satisfazem a condição passada na função.
	- [JavaScript Array filter() Method](https://www.w3schools.com/jsref/jsref_filter.asp)
-  [ ] `.reduce()` é usado para reduzir o array para um único valor.
	- [JavaScript Array reduce() Method](https://www.w3schools.com/jsref/jsref_reduce.asp)
- [ ]  `.find()`

[Curso de JavaScript #11 - map, filter e reduce \(2020\) - YouTube](https://www.youtube.com/watch?v=D\_MExaVe95w&feature=youtu.be)