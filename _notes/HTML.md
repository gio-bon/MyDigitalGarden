---
title: HTML
---

Linguagem de Marcação de HiperTexto é o bloco de construção mais básico da web, utilizada para desenvolver páginas e documentos para a internet garantindo a formatação ideal para sites.
- **Elemento HTML** contêm Tags de abertura e fechamento (as vezes não), atributos e o conteúdo. `<h1 atributo="tal">conteúdo</h1>`
- Comentários
``` html
<!-- Esse comentario não sera exibido -->
```

## Tags
Tags são usadas para renderizar os elementos de uma página, tem uma abertura e fechamento > `<html></html>`
- `<html>` a raiz do documento
- `<head>` é a seção importante de metadados, importante para a otimização do mecanismo de pesquisa (SEO). `<meta>` especifica conjunto de caracteres, descrição de página, palavras-chave, autor do documento e configurações de janela de visualização, não são visualizados diretamente.`<title>` que define o título do documento.
- `<body>` define o corpo do documento

### Semânticas

- `header` é utilizada como um contâiner que contém o conteúdo introdutório ou de navegação da página.
``` html
  <header>
	  <h1>He4rt Devs</h1>
	  <img src="./img/logo.png">
  </header>
```
Não pode ser colocada dentro de uma tag `footer`, `address` ou dentro de outro `header`

- `nav` é utilizada para representar uma seção da página que contém um conjunto de links de navegação
``` html
  <nav>
	  <a *href*="home.html">Home</a>
	  <a *href*="about.html">About</a>
	  <a *href*="contact.html">Contact</a>
  </nav>
```

- `<section>`  é utilizada para definir uma seção da página
``` html
  <section>
	<h2>Linguagens</h2>
	<p>PHP, Javascript, Ruby</p>
  </section>
  - <section>
	<h2>Frameworks</h2>
	<p>Laravel, NodeJS, Ruby on Rails</p>
  </section>
```

- `<article>` é utilizada para especificar um conteúdo independente ou que é destinado a ser distribuido de forma independente ou reutilizável
``` html
  <article>
	<h5>PHP</h5>
	<p>É uma linguagem interpretada livre...</p>
  </article>

  <article>
	<h5>Javascript</h5>
	<p>É uma linguagem de programação interpretada estruturada...</p>
  </article>
```

- `<aside>` é usada para especificar um conteúdo que está relacionado de forma indireta ao conteúdo que está no seu entorno.
``` html
  <p>Programador é alguém que escreve, desenvolve ou faz manutenção de software em um grande sistema ou alguém que desenvolve software para uso em computadores pessoais.</p>
  <aside>
	  <h5>He4rt Devs</h5>
	  <p>A He4rt Developers foi criada com o intuito de guiar quem deseja iniciar na área da programação.</p>
  </aside>
```

- `<footer>` é utilizada para definir o rodapé de um documento ou de uma seção.
``` html
  <footer>
	  <p>He4rt, todos os direitos reservados.</p>
	  <p><a *href*="https://github.com/he4rt">Github</a></p>
  </footer>
```
Fazem parte do rodapé: informações sobre o autor, direitos autorais, links para documentos relacionados, informações de contato.

- `<div>` é utilizada para definir uma divisão ou seção de uma página, também pode ser utilizada como um contêiner para elementos HTML
``` html
  <div>
	  <h2>Nossos serviços</h2>
	  <p>Montagem e manutenção de computadores</p>
  </div>
```

## Atributos
Atributos servem para definir uma propriedade de um elemento HTML e são sempre definidos dentro da tag de abertura, após o nome do elemento, no padrão: `<body bgcolor="red">`

`id` é um atributo global utilizado para definir um identificador exclusivo, único em toda a página.
``` html
  <body>
	  <p id="contato"> Entre em contato </p>
  </body>
```

`class` é um atributo global utilizado para definir uma lista de classes de um elemento, bastante utilizado para definir o css de um grupo de elementos.
``` html
  <body>
	  <p class="paragrafo"> Entre em contato </p>
	  <p class="paragrafo"> Entre em contato </p>
  </body>
```

`link` dentro de `<head>`  é usado para indicar o arquivo `.css` que será usado como para estilizar a página
``` html
	<head>
	 <!-- Aqui adicionamos a tag link, com referência para nosso arquivo CSS -->
	 <link rel="stylesheet" href="css/main.css">
	</head>
```
- `rel`  a relação que esse link tem com nosso arquivo (nesse caso é um stylesheet).
- `href` = a referência de onde esse arquivo está (no nosso caso, dentro da pasta *css* com o nome *main.css*).

`script` é usada para incorporar um script do lado do cliente (JavaScript) `<script src=""></script>`

`style` em elementos é um atributo global utilizado para definir estilos a um elemento, como tamanho, fonte e muito mais
``` html
  <body>
	  <p style="font-size: 12px; color: aquamarine;">Lorem Ipsum</p>
  </body>
```

`href` pode ser utilizado para indicar a URL da página para a qual o link irá redirecionar.
``` html
  <a href="https://www.google.com/">Goole</a>
```
- Com ele também é possível redirecionar a um elemento âncora, mas antes é necessário definir uma id para o elemento.
``` html
  <a href="#sobre">Sobre a empresa</a>
```
- Também é possível redirecionar a uma página, dentro da pasta paginas.
``` html
  <a href="./paginas/contato.html">Contato</a>
```
Ver: `href="mailto:`, `href="urldodownload"`, Link de imagens, `target`

`src` é utilizado para inserir uma imagem em uma página HTML
Com URL **Absoluto** você pode passar o caminho de uma imagem que está hospedada em outro site.
``` html
  <img src="https://heartdevs.com/dist/images/logo-he4rt2.png">
```
Com URL **Relativo** você pode passar o caminho de uma imagem que está hospedada no site.
- URL sem barra: Será utilizado o domínio e o caminho da página atual `<img src="heartdevs.png">`
- URL com barra: Será relativo ao domínio `<img src="/imagens/heartdevs.png">`

O atributo `width` e o atributo `height` é utilizado na tag `img`. Onde o `width` indica a largura e o `height` indica a altura da imagem.
``` html
  <img src="heartdevs.png" width="50" height="50">
```

``` html
  <img src="heartdevs.png" width="50%">
```

`alt` é utilizado na tag `img` para especificar um texto alternativo para uma imagem, caso a imagem não seja exibida por algum motivo.
``` html
  <img src="heartdevs.png" alt="He4rt Devs">
```

`lang`  é utilizado na tag `html`para declarar o idioma da sua página web, auxiliando mecanismos de pesquisa e navegadores `<html lang="pt">`

`title` exibe informações de orientação relacionado ao elemento que ele pertence, assim o valor será exibido ao passar o mouse sobre o elemento `<h1 title="Eu sou um título">HTML4NOOBS</h1>`

`hidden` é utilizado para ocultar elementos no qual ele foi definido e pode ser utilizado em qualquer elemento HTML `<h1 hidden>HTML4NOOBS</h1>`

`align` é utilizado para alinhar elementos da página `<h1 align="left">HTML4NOOBS</h1>`

## Links
`<a>` Define links
`href`  pode ser utilizado para indicar a URL da página para a qual o link irá redirecionar.
``` html
  <a href="https://www.google.com/">Goole</a>
```
Com ele também é possível redirecionar a um elemento âncora, mas antes é necessário definir uma id para o elemento.
``` html
  <a href="#sobre">Sobre a empresa</a>
```
Também é possível redirecionar a uma página, dentro da pasta paginas.
``` html
  <a href="./paginas/contato.html">Contato</a>
```

`href="mailto:` cria links para e-mails com possibilidade de pré-formatação
``` html
  <a href="mailto:salve@salvado.com?subject=Aprendendo&body=Manda um Salve"> Salve?</a>
```
- `Mailto`: Vai ser para qual endereço você vai está enviando email.
- `?`: Vai separar o mailto e subject.
- `Subject`: Qual vai ser o assunto do email.
- `&`: Separa o subject do body.
- `Body`: Vai ser o corpo do email ou texto do email.

`href="urldodownload"`
``` html
  <a href="urldodownload" download="nomedoarquivo.exe">
```
- Em `download` que é onde vamos identificar o nome do arquivo a ser baixado.

Link de imagens: transformar imagens como links
``` html
  <a href = https://heartdevs.com> <img width="100" height="100" src="../assets/logohe4rt.png"></a>
```

`target` tem a função de informar como o link ou redirecionamento deverá ocorrer.
``` html
  <a href="https://heartdevs.com/" target="_blank"> Site da He4rt </a>
```
- `_blank`: abre a página em uma nova janela/aba.
- `_self`: abre a página na mesma janela.
- `_parente`: abre a página na mesma janela do link.
- `_top`: cancela todos os frames e abre a pagina no mesmo navegador.

## Texto
`<p>` cria parágrafos e é um Elemento de bloco
``` html
  <p> Texto </p>
```

`<span>`é uma tag inline que pode ser usada para criar uma seção em um parágrafo que pode ser direcionada usando CSS.
``` html
  <p>Uma parte do texto <span> e aqui outra parte </span></p>
```

`<br>` cria uma quebra de linha
``` html
  <p>Um texto<br>Uma nova linha</p>
```

`<h1> ...` criam títulos, é um Elemento de bloco
``` html
  <h1>Título 1</h1>
  <h2>Título 2</h2>
  <h3>Título 3</h3>
  <h4>Título 4</h4>
  <h5>Título 5</h5>
  <h6>Título 1</h6>
```

`<strong>` marca um trecho de texto como importante, o estilizando em negrito > `<strong>texto</strong>`
- Alternativa visual `<b>`

`<em>` enfatiza um trecho de texto, o estilizando em itálico > `<em>texto</em>`
- Alternativa visual `<i>`

## Multimídia
`<img>` inclui uma imagem dentro da página.
``` html
  <img src = "imagens/he4rt-logo.png" alt = "logo da he4rt">
```
- `src` local de origem da imagem.
-  `alt` informa o texto alternativo da imagem.

`<video>` inclui um vídeo na página
``` html
  <video controls>
	<source src="video.mp4" type="video/mp4">
	<source src="video.ogg" type="video/ogg">
	Seu navegador não possui suporte para Vídeos.
  </video>
```
- `source src` local de origem do arquivo de vídeo;
- `type` tipo de arquivo;

`<audio>` insere um audio
``` html
  <audio controls>
	<source src="musica.ogg" type="audio/ogg">
	<source src="musica.mp3" type="audio/mpeg">
	Seu navegador não possui suporte para áudio.
  </audio>
```
- `source src` local de origem do arquivo de áudio;
- `type` tipo de arquivo;

`<iframe>` têm como função incluir recursos de outra página.
``` html
  <iframe src="https://heartdevs.com/">
	<p>Seu navegador não possui suporte para iFrames.</p>
  </iframe>
```
- `src` local de origem da página a ser exibida;

## Formulário
Exemplo
``` html
  <form action="backend.php">
	<label for="nome">Primeiro Nome:</label>
	<input type="text" id="pnome" name="pnome"><br><br>
	<label for="ultimonome">Último Nome:</label>
	<input type="text" id="unome" name="unome"><br><br>
	<input type="submit" value="Enviar">
  </form>
```
- `form`  está iniciando o formulário;
- `action`  de uma forma simples de explicar, quer dizer o que vai ser feito com esses dados coletados;
- `label for`  a indentificação para a legenda que vai ser exibida;
- `input` têm como função definir um campo de texto;
- `input type`  o tipo que vai ser o campo de entrada de dados;

`<textarea>` têm como função também, definir um campo para o formulário, mas diferentemente, tem como principal característica conter preenchimentos e textos grandes;
`<button>` têm como função definir um botão;
`<select>` têm como função definir uma lista selecionável ou conhecida como "drop-down";
`<option>` têm como função definir uma lista de opções dentro de um "drop-down";
`<optgroup>` têm como função definir um grupo de opções;
`<fieldset>` têm como função definir um grupo de campos;
`<label>` têm como função definir define uma legenda ou nome para um campo de texto ou controle do formulário;
`<output>` têm como função definir elementos de saída para o formulário;
`<legend>` têm como função definir um título para um conjunto de campo;

### Tipos de input
- `<input type="button">`
- `<input type="checkbox">`
- `<input type="color">`
- `<input type="date">`
- `<input type="datetime-local">`
- `<input type="email">`
- `<input type="file">`
- `<input type="hidden">`
- `<input type="image">`
- `<input type="month">`
- `<input type="number">`
- `<input type="password">`
- `<input type="radio">`
- `<input type="range">`
- `<input type="reset">`
- `<input type="search">`
- `<input type="submit">`
- `<input type="tel">`
- `<input type="text">`
- `<input type="time">`
- `<input type="url">`
- `<input type="week">`

## Listas
`<ul>` lista não ordenada
``` html
  <ul>
	  <li>Carro</li>
	  <li>Moto</li>
	  <li>Avião</li>
  </ul>
```
Tipos de marcadores `<ul type="valor">`
- `type="circle"` Círculo não preenchido.
- `type="square"` Quadrado preto.
- `type="disc"` Círculo preenchido.

`<ol>` lista ordenada
``` html
  <ol>
	  <li>Carro</li>
	  <li>Moto</li>
	  <li>Avião</li>
  </ol>
```
Tipos de marcadores `<ol type="valor">`
- `type="1"` Valores inteiros 1,2,3...
- `type="A"` Alfabeto em maiúsculas A,B,C...
- `type="a"` Alfabeto em minúsculas a,b,c...
- `type="I"` Algarismos Romanos em maiúsculo I,II,III...
- `type="i"` Algarismos Romanos em minúsculO i,ii,iii...

`<dl>` lista de descrição
``` html
  <dl>
	  <dt>He4rt Developers</dt>
		<dd>Uma comunidade de desenvolvedores ajudando os iniciantes do mundo da programação.</dd>
	  <dt>4noobs</dt>
		<dd>Projetos desenvolvidos para facilitar o estudos dos devs iniciantes feitos pela nossa comunidade!</dd>
  </dl>
	  ```
- `<dt>` define o nome que será descrito e a tag `<dd>` é a descrição.

## Tabelas
- `<table>` define uma estrutura de tabela.
- `<tr>` define uma linha para tabela.
- `<th>` define o cabeçalho da tabela.
- `<td>` define os dados/células na tabela.

Exemplo
``` html
  <table border="1">
	<tr> <!-- Linha que contêm os cabeçalhos -->
		<th>Cabeçalho 1</th>
		<th>Cabeçalho 2</th>
		<th>Cabeçalho 3</th>
	</tr>
	<tr> <!-- Linha que contêm os dados/células -->
		<td>Célula 1</td>
		<td>Célula 2</td>
		<td>Célula 3</td>
	</tr>
	<tr> <!-- Linha que contêm os dados/células -->
		<td>Célula 4</td>
		<td>Célula 5</td>
		<td>Célula 6</td>
	</tr>
  </table>
```

---

[[Refs HTML]]

<style>
  .body {
    max-width: 46em;
  }
</style>
