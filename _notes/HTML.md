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
    <section>
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
