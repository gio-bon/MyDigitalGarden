---
title: JSON
---

- JSON (JavaScript Object Notation) é um formato para compartilhar dados e é derivado do JavaScript, mas está disponível para uso em muitas outras linguagens.
- O atributo mais importante do JSON é que ele pode ser facilmente transferido entre as linguagens de programação em um formato com o qual todas as linguagens participantes podem trabalhar. Os objetos JavaScript só podem ser trabalhados diretamente por meio da linguagem de programação JavaScript.
- Muito legível e leve, JSON oferece uma boa alternativa ao XML e requer muito menos formatação.
- Um objeto JSON é um formato de dados `chave : valor` que normalmente é renderizado entre chaves `{ }`. Ao trabalhar com JSON, provavelmente você verá objetos JSON em um arquivo `.json`, mas eles também podem existir como um objeto JSON ou string no contexto de um programa.

``` js
  {
	"primeiro_nome" : "Brena",
	  "sobrenome" : "Mulenga",
	  "endereco" : "Rua das Femeas, 766",
	  "idade" : 22
  }
```

- As **chaves** JSON estão no lado esquerdo dos dois pontos. Eles precisam ser colocados entre aspas duplas, como em "key", e podem ser qualquer string válida. Dentro de cada objeto, as chaves precisam ser exclusivas. Essas strings de chave podem incluir espaço sem branco, como em `"primeiro nome"`, mas isso pode dificultar o acesso durante a programação, então é melhor usar sublinhados, como em `"first_name"`.
- Os **valores** JSON são encontrados à direita dos dois pontos. No nível granular, eles precisam ser um dos 6 tipos de dados simples.
- Embora em arquivos `.json`, normalmente veremos o formato expandido em várias linhas, JSON também pode ser escrito em uma linha.

``` js
{ "primeiro_nome" : "Breno", "sobrenome" : "Martins", "endereco" : "Rua do Machos, 665", "idade" : 55 }
```

- É importante ter em mente que, embora pareçam semelhantes, um objeto JSON não tem o mesmo formato de um objeto JavaScript, portanto, embora você possa usar funções dentro de objetos JavaScript, não pode usá-los como valores em JSON.
- O JSON pode se tornar hierárquico e complexo, composto de objetos e matrizes aninhados.

``` js
  [

	{
	  "name": "Molecule Man",
	  "age": 29,
	  "secretIdentity": "Dan Jukes",
	  "powers": [
		"Radiation resistance",
		"Turning tiny",
		"Radiation blast"
	  ]
	},
	{
	  "name": "Madame Uppercut",
	  "age": 39,
	  "secretIdentity": "Jane Wilson",
	  "powers": [
		"Million tonne punch",
		"Damage resistance",
		"Superhuman reflexes"
	  ]
	}
  ]
```

- Na maioria das vezes, você não escreverá JSON puro, mas o extrairá de fontes de dados ou converterá outros arquivos de dados em JSON. Você pode converter CSV ou dados delimitados por tabulação.
- Em muitos aspectos, o XML é muito semelhante ao JSON, mas requer muito mais texto, por isso é mais longo e consome mais tempo para ler e escrever. XML deve ser analisado com um analisador XML, mas JSON pode ser analisado com uma função padrão. Além disso, ao contrário do JSON, o XML não pode usar matrizes.

---

[An Introduction to JSON | DigitalOcean](https://www.digitalocean.com/community/tutorials/an-introduction-to-json)
- [ ] [How To Work with JSON in JavaScript | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-work-with-json-in-javascript)
- [ ] [Como usar JSON.parse\(\) e JSON.stringify\(\) | DigitalOcean](https://www.digitalocean.com/community/tutorials/js-json-parse-stringify-pt)