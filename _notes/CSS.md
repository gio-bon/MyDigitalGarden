---
title: CSS
---

Cascading Style Sheet, ou folhas de estilo em cascata serve para possamos estilizar as páginas escritas em HTML, fazendo com que elas fiquem mais bonitas e agradáveis aos usuários finais.

## Definindo o CSS

Em elementos, `style` é um atributo utilizado para definir estilos a um elemento, como tamanho, fonte e muito mais.

``` html
  <body>
	  <p style="font-size: 12px; color: aquamarine;">Lorem Ipsum</p>
  </body>
```

Em `<head>` o CSS é aplicado apenas à página em questão
``` html
	<head>
	<!-- Adicionamos a tag style aqui para podermos estilizar nossa página -->
	  <style>
		.box-red {
		  background-color: red;
		  width: 100px;
		  height: 100px;
		}
	  </style>
	</head>
	<body>
```

Dentro de `<head>`  `link` é usado para indicar o arquivo `.css` que será usado como para estilizar a página
``` html
	<head>
	 <!-- Aqui adicionamos a tag link, com referência para nosso arquivo CSS -->
	 <link rel="stylesheet" href="css/main.css">
	</head>
```
- `rel` = a relação que esse link tem com nosso arquivo (nesse caso é um stylesheet).
- `href` = a referência de onde esse arquivo está (no nosso caso, dentro da pasta *css* com o nome *main.css*).

## Regra CSS
	- Composto por seletores, propriedades e valores.
```css
  seletor {
	propriedade: valor;
		propriedade: valor;
	...
  }
```

## Seletores
### Elemento
Para selecionar qualquer elemento pela Tags dele

``` html
	  <div id="exemplo"></div>
```

``` css
	  div {
	  width: 100px;
	  height: 100px;
	  background-color: red;
	  }
```
### ID
Para selecionar qualquer elemento pelo o `id` dele, devemos colocar uma cerquilha `#` antes de colocar qual o id do elemento.

``` html
	  <div id="exemplo"></div>
```

``` css
	  #exemplo {
	  width: 100px;
	  height: 100px;
	  background-color: red;
	  }
```

### Classe
Para selecionar qualquer elemento pela `class` , devemos colocar um ponto final `.` antes de referenciar pela classe

``` html
	  <div class="exemplo"></div>
```

``` css
	  .exemplo {
	  width: 100px;
	  height: 100px;
	  background-color: red;
	  }
```

### Atributo
Podemos também selecionar pelo Atributos usando colchetes `[ ]` colocando o nome do atributo e opcionalmente um operador seguido pelo valor dele.

``` html
	  <div class="exemplo">
	  <button type="button"></button>
	  </div>
```

``` css
	  /* Estamos pegando todos os elementos que tem o atributo type com valor "button" */
	  [type='button'] {
	  width: 100px;
	  height: 100px;
	  background-color: red;
	  }
```

## Pseudo-seletores
`*` é usado para resetar o css que vem "por padrão", assim temos todo os elementos da página como alvo.

``` css
	  * {
		padding: 0;
		margin: 0;
		outline: 0;
		box-sizing: border-box;
	  }
```

A `>` B irá selecionar os filhos B que são diretos de A. No exemplo a seguir, todos os filhos de ul que são li serão afetados:

``` css
	  ul > li {
		color: white;
	  }
```

A `+` B irá selecionar somente o elemento imediatamente(B) após o primeiro(A) elemento. No exemplo a seguir, ele irá chamar o segundo span, e não o primeiro.

``` css
	  span + span {
		color: white;
	  }
```

A `~` B é parecido com o A + B, com a diferença que irá selecionar todos os elementos imediatamente após B

``` css
	  ul ~ section {
		background-color: red;
	  }
```
			  
## Pseudo-Classes
Pseudo-classes definem um estado especial de um elemento, como por exemplo `:hover` para quando se está com o mouse em cima de um elemento

``` css
	  seletor:pseudo-classe {
		propriedade: valor;
	  }
```
- `:active`  é utilizada em links e botões, define se um elemento alvo está ativo pela navegação do usuário
- `:focus` é aplicado quando o elemento recebe foco
- `:hover` para quando está com o mouse em cima
- `:visited` para link que já foi visitado

## Tipos de Valores
### Cores
Podemos manipular a cor dos textos usando `color: <cor-aqui>` de várias formas diferentes:
- Nome: `background-color: red`
- HEX: `color: #AAAAAA` usando o hexadecimal de uma cor
- HSV: `color: hsl(0, 100%, 50%)`
- RGB `color: rgb(255, 0, 0)`
- RGBA `color: rgba(255, 0, 0, 0.5)` O parâmetro `0.5`, ou alfa, possibilita definir a opacidade de uma cor

### Unidades
#### Absolutas
Irão aparecer do tamanho exato que você definir na tela. Por exemplo, se você definir que o o `width` de um elemento é *100px*, ele será *100px* independente do tamanho da tela do dispositivo que você estiver usando.
- Píxels `px`
- Points `pt`
- `in` (inches/polegadas)
- Centímetro e Milímetro `cm` / `mm`
- Paica `pc`

### Relativas
Especificam o tamanho relativo em relação com outra propriedade de tamanho. Essas medidas escalam melhor na renderização de dispositivos de tamanhos diferentes.
- A unidade de medida `rem` é relativa ao tamanho da fonte do elemento root.
- A unidade de medida `vw` equivale a 1% do `width` do viewport.
- A unidade de medida `vh` equivale a 1% do `height` do viewport.
- Porcentagem `%`

## Propriedades
### Fontes
- Estilo
``` css
	  p {
		font-style: italic;
	  }
```

- Peso
``` css
	  h1 {
		font-weight: bold;
	  }
```
		
- Importação
``` css
	  @import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
	  - p {
	  font-family: "Poppins", "sans-serif";
	  }
```

### Background
`background-color` define a cor de fundo
``` css
	  elemento {
		background-color: valor;
	  }
```

`background-image` imagem como plano de fundo
``` css
	  elemento {
		background-image: url('');
	  }
```

`background-repeat` caso a imagem não tenha tamanho suficiente para preencher toda área necessária, ela irá repetir na horizontal e na vertical até que toda área seja preenchida. Para controlarmos essa repetição usamos a propriedade `background-repeat`.
``` css
	  elemento {
		background-image: url('imagem/img1.png');
		background-repeat: valor;
	  }
```

Os valores podem ter quatro padrões:
- no-repeat: você pode definir que a imagem não se repita. Ex: `background-repeat: no-repeat`
- repeat: você pode definir que a imagem se repita tanto na horizontal como na vertical. Ex: `background-repeat: repeat`
- repeat-x: você pode definir que a imagem se repita apenas na horizontal. Ex: `background-repeat: repeat-x`
- repeat-y: você pode definir que a imagem se repita apenas na vertical. Ex: `background-repeat: repeat-y`

`background-attachment` você pode definir se a imagem ficará fixada ou se ela irá se mover de acordo com o scrool.
``` css
	  elemento {
		background-image: url('imagem/img1.png');
		background-attachment: valor;
	  }
```
			  
Os valores podem ter dois padrões:
- fixed: você pode definir que a imagem fique fixada. Ex: `background-attachment: fixed`
- scrool: você pode definir que a imagem se mova com o scrool. Ex: `background-attachment: scroll;`

`background-position` você pode definir a posição inicial em que a imagem irá se posicionar.
``` css
	  elemento {
		background-image: url('imagem/img1.png');
		background-position: valor;
	  }
```

### Border
Define a borda em relação ao estilo, largura e cor `border: [border-width] [border-style] [border-color];`
``` css
	  border: 5px solid #c6c6c6;
```

- `border-width` define qual a largura será aplicada para a borda
``` css
	  border-style: solid;
	  border-width: 5px;
```

- `border-style` define qual estilo a sua borda terá, podendo aplicar um estilo único para todo o elemento ou definir até 4 tipos diferentes, sendo um para cada lado do elemento (superior, inferior, esquerda e direita).
``` css
	  border-style: double dotted solid dashed;
```
Você pode aplicar os seguintes estilos:
- `dotted` - A borda será preenchida com pontos
- `dashed` - A borda será preenchida com traços
- `solid` - A borda possuirá um preenchimento sólido
- `double` - A borda será composta por dois traços sólidos
- `groove` - Aplica um padrão de sombra com aparência 3D
- `ridge` - Aplica um padrão de sombra elevada com aparência 3D
- `inset` - Aplica um padrão de sombra em baixo relevo com efeito 3D
- `outset` - Aplica um padrnao de sombra em alto relevo com efeito 3D
- `none` - Não exibe borda no elemento
- `hidden` - Oculta a borda do elemento

- `border-color` define qual cor será aplicada na borda
- `border-radius` permite adicionar bordas arredondadas no elemento, podendo ser aplicado de 1 a 4 valores.
``` css
	  border-radius: 125px 100px 50px 20px;
```

### Position
A propriedade `position` define para o posicionamento dos elementos.
`position: static` é o valor default de todos os elementos.
- [ ] `position: absolute`
- [ ] `position relative`
- [ ] `position: fixed`
- [ ]  `position: sticky`

### Display
Display influencia na forma como os elementos são dispostos na tela.
- `display: block`
	- Ele sempre ocupa todo espaço disponível na horizontal e sempre começará a partir de uma nova linha.
	- É importante você ter em mente quais elementos possuem display block por padrão: `div`, todos elementos de título (h1 ao h6), `p`, `form`, `header`, `footer`, `section`.
- `display: inline`
	- O display inline também possui um funcionamento bastante simples, podemos dizer que se o display block ocupa todo espaço disponível, o display inline é totalmente o contrário, ocupando somente o tamanho correspondente ao seu conteúdo.
- `inline-block`
	- É uma "junção" dos dois anteriores, mas com ele você tem um comportamento inline, ou seja, por padrão o elemento irá ocupar o espaço demandado pelo seu conteúdo, mas com uma característica herdada do display block, você pode setar o tamanho (largura e altura) que desejar sem restrições.
- `box-shadow`
- É utilizado para adicionar efeitos de sombra em volta de um elemento, descrita pelo deslocamentos (offset) X e Y em relação ao elemento, desfoco, propagação do raio e cor.
``` css
	  div {
		box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
	  }
```
- O primeiro valor `2px` equivale ao eixo x da pagina `offset-x`.
- O segundo valor `2px` equivale ao eixo y da pagina `offset-y`.
- O terceiro valor `2px` equivale ao blur, que a sombra vai ter `blur-radius`.
- E o ultimo atributo `rgba(0, 0, 0, 0.2)` é a cor que essa sombra vai receber `color`.
O [Box-shadow generator](https://www.cssmatic.com/box-shadow) é uma ferramenta interativa que permite a criação de box-shadow.

- [ ] `z-Index` comportamento de camadas do CSS, o padrão é `z-index: 0`
- [ ] `transition` transições de elementos
		
## Box Model
Box model é basicamente uma caixa, um box, que está envolta de cada elemento HTML. Ela é composta por margem, bordas, preenchimento e o conteúdo.

- `padding` ou o preenchimento, logo após o conteúdo e é transparente.
- `border` é uma borda que fica ao redor do seu padding.
- `margin` é a camada mais externa, irá determinar as distâncias para os outros elementos e é transparente.

O tamanho final do elemento será uma somatória de todas as medidas que você definiu para as propriedades `padding`, `border` e `margin` além do width e height

## Variáveis
Utilizamos o `var(<variavel>)` para indicar que estamos chamando uma variável do CSS. A utilização mais comum é setar as variáveis em um arquivo base de CSS, utilizando o `:root`

``` css
	  :root {
		--text-primary: red;
	  }
```

Utilizando a variável:
``` css
	  section {
	  background-color: var(--text-primary);
	  }
```

---

[[Refs CSS]]