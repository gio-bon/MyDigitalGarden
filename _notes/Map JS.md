---
title: Map JS
---

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