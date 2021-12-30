---
title: DOM
---

Sempre que uma página é carregada, o navegador cria um *DOM* (Document Object Model) para a gente. Com este *DOM* criado, podemos acessar e mudar qualquer elemento utilizando o javascript. Basicamente, o DOM define um maneira de pegar(`get`), mudar(`change`), adicionar(`set`) ou deletar(`delete`) cada elemento HTML no DOM.

O DOM define:
- Os elementos como objetos,
- As propriedades dos elementos,
- Os métodos,
- Os eventos.

## Acesso a elementos
- `document.getElementById(id)` encontra um elemento por seu Id.
- `document.getElementsByTagName(tag)` encontra um elemento pela sua tag HTML.
- `document.querySelector("[data-attribute]")` encontra um elemento por seu data-attribute.
- `document.getElementsByClassName(nome)` encontra um elemento pela classe.
- `document.querySelector(nome)` encontra o primeiro elemento com o valor informado (id, nome, tag, data-attribute)
- `document.querySelectorAll(name)` encontra todos os elementos com o valor informado (id, nome, tag, data-attribute)

## Alteração de elementos
- `element.innerHTML = new html content ` altera o HTML interno de um elemento
	- `document.getElementById(id).innerHTML = new HTML();`
- `element.attribute = new value` altera o valor do atributo de um elemento HTML
	- `document.getElementById(id).attribute = new value;`
- `element.style.property = new style` altera o estilo de um elemento HTML
	- `document.getElementById(id).style.property = new style;`
- `element.setAttribute(attribute, value)` altera o valor do atributo de um elemento HTML

[Lista](https://www.w3schools.com/jsref/dom_obj_style.asp) de propriedades que podem ser alteradas.

## Adicionar ou remover elementos
- `document.createElement(element)` cria um elemento HTML
- `document.removeChild(element)` eemove um elemento HTML
- `document.appendChild(element)` adiciona um elemento HTML
- `document.replaceChild(new, old)` substitui um elemento HTML
- `document.write(text)` escreve no fluxo de saída HTML

## Event Handlers
Um evento é a ocorrência de uma ação, geralmente produzida por um usuário, em uma página. A partir da programação dos eventos é feita a interatividade da página. Podemos executar um script quando um evento ocorre.

- **eventos de interface do usuário** (`load`, `unload`,  `resize`),
- **eventos de mouse** (`click`, `dblclick`, `mouseover`),
- **eventos de teclado** (`keypress`, `keydown`, `keyup`)
- **eventos de formulário** (`change`, `focus`, `blur`).
- Os eventos `onload` e `onunload` são acionados quando o usuário entra ou sai da página.
- O evento `onchange` é frequentemente usado em combinação com a validação dos campos de entrada.
- Os eventos `onmouseover` e `onmouseout` podem ser usados para disparar uma função quando o usuário passa o mouse sobre ou fora de um elemento HTML.
- Os eventos `onmousedown`, `onmouseup` e `onclick` são todos partes de um clique do mouse. Primeiro, quando um botão do mouse é clicado, o evento `onmousedown` é acionado; depois, quando o botão do mouse é liberado, o evento `onmouseup` é acionado; finalmente, quando o clique do mouse é concluído, o evento `onclick` é acionado.
- `onfocus` altera atributos quando um campo de entrada recebe o foco.

### Formas antigas de adicionar evento
- No próprio html: `<button onclick="fazAlgumaCoisa()">Try it</button>`
- No DOM com onclick: `document.getElementById("myBtn").onclick = fazAlgumaCoisa;`

## Event Listener
É possível acrescentar “ouvintes” para essas ações nos elementos da página e chamar funções no momento em que cada uma dessas ações ocorrer. Você pode adicionar ouvintes de eventos a qualquer objeto DOM, não apenas aos elementos HTML, ou seja, o objeto da janela.

O método `addEventListener('evento', função)` anexa um manipulador de eventos ao elemento especificado, facilitando o controle de como o elemento reage a cada interação com o usuário.
- O primeiro parâmetro é o tipo de evento (como explicado em Event Handlers)
- O segundo parâmetro é a função que queremos chamar quando o evento ocorrer.

``` js
  let botao = document.getElementById('id-tal');
  function funcaoTal(event){
	//comandos
  }
  botao.addEventListener('click', funcaoTal);
```

Ou ainda, com a função acoplada:

``` js
  let botao = document.getElementById('id-tal');
	botao.addEventListener('click', function(event){
	//comandos 
  });
```

Quando é preciso capturar um evento de click em muitos elementos com a mesma classe (use o `forEach`).

``` js
  let botoes = document.querySelectorAll('.class-tal');
	function funcaoTal(event){
	//comandos
  }
  botoes.forEach(function(key){
	key.addEventListener('click', funcaoTal);
  }
```

Quando dois ouvintes de evento vão para a mesma função, há como diferenciar o tipo de evento capturado com `event.type`.

``` js
  let botao = document.getElementById('id-tal');
  function funcaoTal(event){
	console.log(event.type) //click ou keydown e há como diferenciar
  }
  botao.addEventListener('click', funcaoTal); //1 ouvinte de evento
  window.addEventListener('keydown', funcaoTal); //2 ouvinte de evento
```