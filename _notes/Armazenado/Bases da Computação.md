---
title : Bases da Computação
---
## Eletrônica
Em essência, a eletrônica busca controlar a corrente elétrica ou Eletricidade. Para isso usará os componentes eletrônicos (resistores, capacitores, indutores e transistores).

Até os sistemas eletrônicos absurdamente complicados, que consistem em uma parafernália confusa de componentes, fazem os mesmos tipos de coisa que os circuitos simples: manipulam a corrente elétrica para realizar uma tarefa.

Nos sistemas computacionais os padrões de energia elétrica armazenada são usados para representar números. Esses padrões são manipulados usando-se componentes eletrônicos.

Há muitos e muitos **componentes eletrônicos** que ajudam a controlar a energia elétrica nos circuitos. Entre os componentes mais populares estão os **resistores**, que restringem o fluxo da corrente, e os **capacitores**, que armazenam energia elétrica. **Indutores** e **transformadores** são dispositivos que armazenam energia elétrica em campos magnéticos. Os **diodos** são usados para restringir o fluxo da corrente em uma direção, de forma muito semelhante às válvulas, enquanto os Transistores são componentes versáteis usados para ligar e desligar circuitos, ou amplificar a corrente.

## Eletricidade
Tem a ver com os átomos, pois em seu núcleo há os prótons e nêutrons (de cargas positiva e neutra) e girando em volta do núcleo há os eletrons (carga negativa). Cargas diferentes se atraem e cargas iguais se repelem.

Alguns materiais conduzem bem os eletrons entre os átomos, como o cobre, o que faz deles materiais condutores. Já outros dificultam muito essa corrente de transferência (corrente elétrica) de protons, pois já são estaveis (precisando de uma tensão muito alta para fazerem essa condução elétrica, como um raio se propagando pelo ar), sendo materiais isolantes.

Corrente elétrica é o deslocamento de elétrons livres de átomo em átomo seguindo uma única direção. A tensão (DDP, diferença de potencial ou ainda voltagem) é a força que faz com que os eletrons se desloquem.

Em uma bateria há o lado negativo (átomos com mais elétrons) e o positivo (átomos com menos). Ao colocar um fio condutor entre os polos os átomos transferem os elétrons (dos que tem elétrons sobrando em relação ao núcleo, para os que tem faltando, lembrando que o número de prótons e eletrons devem ser iguais para que ele seja estável) criando a corrente elétrica. Essa força dos elétrons indo de um lado para o outro é medido em volts.

As fontes de energia convertem a energia mecânica, química, térmica ou luminosa em eletricidade, para fazer coisas.

Conceitos mais avançados, de como a eletricidade é gerada: corrente contínua (DC) e corrente alternada (AC).
- A **corrente contínua**: a pilha contém dois metais imersos em liquido que interage com metal, de um lado criando cargas negativas e do outro positivas. Ao se ligar os dois polos a corrente elétrica flui continuamente enquanto houver a diferença de estados.
- Na **corrente alternada**: uma usina hidrelétrica usa correntes de água pra produgir energia mecânica (pás girando). Ao se utilizar fios e imãs é possivel induzir a eletricidade no fio, por causa da relação entre o magnetismo e a eletricidade. É alternada porque a cada giro de 180 graus do imã a corrente elétrica muda temporariamente de direção.

Basicamente a alternada tem voltagem bem maior e pode percorrer distâncias bem maiores do que a contínua. No sistema residencial ela é convertida para corrente contínua, para que possa ser usada pelos aparelhos.

## Transístor
Deve ser entendido como uma espécie de chave, mas ao invés de ser acionada mecanicamente é ativada com um impulso elétrico.

Tem 3 terminais (pinos), o coletor, a base e o emissor. Essencialmente a corrente que vai para o coletor é classificada em baixa voltagem (0 ou falso) ou alta voltagem (1 ou verdadeiro), aceitando níveis ligeiramente do ideal.

É possível formar circuítos com transistores, chamados de Portas Lógicas.

## Portas Lógicas
São pequenos circuítos que usam transistores que executam operações lógicas sobre corrente elétrica, recebendo uma ou mais entradas e devolvendo uma saída lógica. Essas portas são operações/cálculos na algebra de Álgebra Booleana.

A lógica digital é baseada em portas (*gates*) ou interruptores digitais. Seu objetivo é produzir uma única saída filtrando as entradas de acordo com determinada lógica binária (função implementada no circuito). Ao combinar sinais binários é possível criar mais representações (2 lâmpadas podem representar $2^2$ estados, 3 lâmpadas podem representar $3^2$ estados...). Essas combinações são analisadas em tabelas verdade.

As operações lógicas em dígitos binários podem ser combinadas para realizar cálculos genéricos. Uma porta lógica recebe valores através de fios de entrada, realiza sua operação e coloca o resultado em seu fio de saída. Grupos de variáveis lógicas podem representar números em formato binário. Verdadeiro e Falso são representados por correntes elétricas de alta ou baixa tensão.
- A porta `NOT` (negação) inverte o sinal da entrada.
- A porta `AND` (conjunção) terá saida 1 apenas se todas as entradas forem 1, caso contrário retorna 0.
- A porta `OR` (disjunção) apresenta 1 como saída se pelo menos uma das entradas forem 1.
- As outras portas são o resultado da combinação das portas anteriores: porta `NAND`, `NOR` e `XOR`.

Essas portas são usadas em circuitos elétricos que podem realizar cálculos em velocidades muito altas (podem ser computadas quase instantaneamente). Para aproveitar esta forma rápida de computação, transformamos os problemas numéricos em sua forma binária/lógica.

Os princípios de trabalho da CPU moderna são baseados em álgebra booleana. Uma CPU moderna é apenas um circuito de milhões de fios microscópicos e portas lógicos que manipulam correntes elétricas de informação.

## Álgebra Booleana
George Boole foi um matemático e filósofo britânico criador da álgebra booleana e escritor de Investigação das leis de pensamento. Ele traduz a lógica em algo matemático (não filosófico) podendo existir em axiomas simples, sendo reduzida a operadores lógicos de E, OU e NÃO trabalhando em um sistema binário.

> Com dígitos binários, máquinas podiam seguir instruções lógicas e sua matemática ficava perfeitamente adaptada ao circuito elétrico ligado/desligado. Em conseqüência, o dígito binário (ou bit) iria acabar se tornando a unidade fundamental de informação em sistemas de computador.

Ao aprender a **lógica formal**, podemos usá-la deliberadamente para resolver problemas.
Em matemática comum, variáveis e operadores (+, ×, -, …) são usados para modelar problemas numéricos. Na lógica matemática, as variáveis e os operadores **representam a validade das coisas**. Eles não expressam valores numéricos, mas valores Verdadeiro/Falso. 
Por exemplo, a validade da expressão _“se a piscina estiver quente, eu vou nadar”_ é baseada na validade de duas coisas, que podem ser mapeadas para as variáveis lógicas `A` e `B`.
- `A` : A piscina está quente. (Verdadeiro significa uma piscina quente)
- `B` : Eu nado. (Falso significa não nadar)

Para negar as ideias, nós usamos `!`, o operador da negação. `!A` é o oposto de `A`:
- `!A` : A piscina é fria.
- `!B` : Eu não nado.

`B` não pode ser metade verdade, porque eu não sei nadar pela metade. A dependência entre as variáveis é expressa com `→`
- O operador condicional. `A → B` é a ideia que `A = True` implica `B = True`:
- `A → B` Se a piscina estiver morna, então eu nadarei.

### Contrapositivo
Dado `A → B` e eu não nadei, o que pode ser dito sobre a piscina? Uma piscina quente força a natação, portanto, sem nadar, é impossível que a piscina esteja quente.

Cada expressão de condição tem um equivalente contrapositivo: para quaisquer duas variáveis A e B, `A → B` é o mesmo que `!B → !A`.

Outro exemplo: se você não sabe escrever um bom código, você não leu este livro. Seu contraponto é que se você ler este livro, você pode escrever um bom código. Ambas as sentenças dizem o mesmo de maneiras diferentes.

### Bicondicional
Tenha cuidado, ao dizer que “se a piscina estiver quente, eu vou nadar” não significa que eu só vou nadar em água quente. A declaração não promete nada sobre piscinas frias.
Em outras palavras, `A → B` não significa `B → A` ("Eu nado se a piscina estiver quente).

Para expressar ambos os condicionamentos, use o biconditional: `A ↔ B`:
- Eu nadarei se e somente se a piscina estiver morna.
- Aqui, o fato de a piscina estar morna é equivalente à minha natação: saber sobre a piscina significa saber se vou nadar e vice-versa.

### Propriedades
Assim como a álgebra elementar simplifica as expressões numéricas, **a álgebra booleana simplifica as expressões lógicas**. As regras a seguir transformam modelos lógicos, **revelam propriedades e simplificam expressões**.

#### Associabilidade
Os parênteses são irrelevantes para sequências de operações AND ou OR. Como sequências de somas ou multiplicações em álgebra elementar, elas podem ser calculadas em qualquer ordem.
- `A AND (B OR C) = (A AND B) OR (A AND C)`
- `A OR (B AND C) = (A OR B) AND (A OR C)`

#### Distributividade
Em álgebra elementar, nós fatoramos multiplicativos de somas:
- `a × (b + c) = (a × b) + (a × c)`.

Da mesma forma na lógica:
- `A AND (B OR C) = (A AND B) OR (A AND C)`.
- `A OR (B AND C) = (A OR B) AND (A OR C)`.

#### Lei DeMorgan
Não pode ser verão e inverno de uma só vez, portanto, ou não é verão ou não é inverno.
E não é verão e não é inverno se não for verão ou inverno.
Seguindo este raciocínio, ANDs podem ser transformados em ORs e vice versa:
- `!(A AND B) = !A OR !B`,
- `!A AND !B = !(A OR B)`

## Allan Turing
Matemático britânico escritor de *On Computable Numbers* (parte teórica da computação, pelo qual realmente ficou conhecido) que define os limites e possibilidades teóricas de qualquer computador através do conceito da Máquina de Turing.

Chegou a conhecer John Von Neumann que se deu conta das possibilidades práticas da computação (disciplina praticamente criada por Allan).

### Máquina de Turing
Foi o protótipo conceitual de um computador, antes mesmo de algum computador eletrônico existir. Conceitualmente é uma fita infinita (com vários quadrados que armazenam dígitos binários) e uma cabeça de leitura ou gravação que percorre essa fita em qualquer uma das direções. Ela seria capaz de simular outras maquinas de Turing dentro dela.

## Programação
Basicamente, programação é tentar fazer com que um computador conclua uma tarefa específica sem cometer erros. A principal funcionalidade de um computador é sua versatilidade, e vem da forma como o manipulamos para atender às nossas necessidades.

Imagine que seu amigo é o the flash, e ele é capaz de fazer quase tudo o que você lhe pedir na velocidade da luz. Mas há duas desvantagens nele, ele é extremamente burro pois precisa que lhe deem orientações pormenorizadas sobre como deve fazer as tarefas. Ao mesmo tempo ele não fala o mesmo idioma que você, e toda vez que tenta explicar o que ele deve fazer você precisa traduzir essas instruções. Esse é o computador.

O computador não fala o mesmo idioma que você, ele só entende o código de máquina (binário) que é muito difícil de pessoas entenderem, e se tentassem levaria um tempo enorme. Cada instrução dada ao computador precisa ser convertida em uma string de zeros e uns e depois interpretada pelo computador para realizar uma tarefa.

Uma linguagem de programação serve para traduzir nossas instruções humanas para a linguagem que os computadores entendem. Elas são linguagens intermediárias e também muito mais fáceis de entender e aprender.

O que é conhecido como Lógica de Programação nada mais é a forma de pensar correta quando se passa as instruções que o computador deve cumprir, utilizando de certas estruturas predefinidas que as linguagens de programação já possuem.

## Abstração
Significa ocultar o funcionamento subjacente de um sistema com atalhos ou conveniências, adicionando complexidade para que você possa fingir que ela não existe. Uma abstração simplificará um processo ou artefato, fornecendo o que você realmente precisa e ocultando os detalhes inúteis que você não se importa.
Três principais propriedades de uma abstração:
- O conceito de esconder ou remover o que é inútel.
- O conceito de generalização (generalização de uma ideia ou conceito)
- O conceito de ideia versus realidade, lidando com uma ideia que representa a realidade.

Na programação, algumas abstrações são implementadas por meio de indireção. Objetos, métodos, herança e padrões de projeto não são coisas reais, assim também como não são as variáveis, loops ou funções. São tudo abstrações. Sem a abstração, qualquer coisa que se tentasse fazer em computação seria um inferno, pois teríamos de pensar nos detalhes de implementação de tudo o tempo todo

A abstração pode ser em camadas, ou seja, você pode abstrair uma abstração. Afinal, uma abstração pode precisar de mais simplificação ou generalização. A barreira de abstração existe pois a camada de abstrações é normalmente isolada.

### Camadas de abstração de um software
Cada vez mais você descerá nas camadas de abstração, cada vez mais você se afastará do mundo que vivencia todos os dias. Você se encontrará em lugares mais esotéricos, como gerenciamento de memória e especificações de hardware. A mecânica quântica está ainda mais além do que vivenciamos diariamente.
- Interface de usuário.
- Linguagem de alto nível
- Linguagem de baixo nível (C).
- Linguagem de máquina.
- Arquitetura (registros, memória, unidade aritmética…).
- Elementos de circuito (portas lógicas).
- Transistores.
- Física do estado sólido.
- Mecânica quântica.

## Indireção
Na programação de computadores, a indireção é a capacidade de fazer referência a algo usando um nome, referência ou contêiner em vez do próprio valor. É o ato de fazer referência para alguma coisa indiretamente, ou seja, através de algo que não seja o seu valor. Usamos isso em programação o tempo todo sem perceber.
- Uma **variável** é uma indireção. Poderíamos acessar uma posição da memória, mas usamos um nome que nos leva a essa posição da memória.
- Uma **função** é outra das mais usadas. A função nada mais é que um nome que referencia uma posição de memória onde tem um código. O uso direto é acessar o código logo ali, mas o que fazemos é indicar onde o código está. É um acesso indireto, portanto é uma indireção.
- Um **array** simples é uma indireção. Ele funciona como uma variável de uma variável. A variável primária é o array como um todo, a variável secundária é o elemento individual dele.

Outro exemplo importante é o sistema de nomes de domínio, o que permite que nomes como `en.wikipedia.org` sejam usados no lugar de endereços de rede como `208.80.154.224`. A indireção de nomes legíveis por humanos para endereços de rede significa que as referências a uma página da Web se tornam mais memoráveis e os links não precisam ser alterados quando um site é realocado para um servidor diferente.

Pontos-chave da relação entre abstração e indireção:
- Algumas abstrações criam indireções, como uma classe abstrata ou uma construção de interface.
- Criar uma indireção não significa criar uma abstração (útil).
- Indireções podem tornar seu software mais flexível a mudanças (a custo de maior complexidade. Certifique-se de que você precisa dessa flexibilidade.

## Lógica e Linguagens de programação
Para ser realmente bom em programação, você não precisa estudar nenhuma grande coisa em particular. Você precisa praticar e entender as pequenas coisas, repetidamente, até que se tornem uma segunda natureza. Você quer ser capaz de trabalhar tão rápido com o básico absoluto, rápido o suficiente para que você não precise pensar nisso.

A base da computação é a **abstração**. Domine os fundamentos, entenda como eles são compostos em abstrações e a partir daí você poderá entender quase qualquer coisa à medida que avança.

O volume de software existente é enorme, há centenas de ecossistemas, milhares de ferramentas, milhões de bibliotecas e se você tentasse aprendê-los todos como coisas individuais, seria impossível. No entanto, todos são construídos com as mesmas partes básicas.

### Linguagens de programação
Linguagens de programação são usadas para implementar algoritmos, enquanto que algoritmos são criados para resolver problemas, criando programas que passam instruções para o computador.

Nessas linguagens, há estruturas de entrada e saída de dados, cálculos, processos de decisão com base em condições a serem cumpridas e repetições de blocos de códigos por um certo número de vezes ou até que determinadas condições sejam alcançadas.
São classificadas de acordo com a proximidade da linguagem e compreensao humana:
- De alto nível se humanos podem ler e compreender facilmente, exemplo javascript e python.
- De baixo nível se estiverem mais perto  do código binário, sendo assim mais rápidas, porém mais dificultosas de humanos lerem e compreenderem, por exemplo Assembly e C.

Para que a CPU possa executar um programa, executando os cálculos, é necessário converter uma linguagem de baixo ou alto nível em código de máquina, e isso é feito por meio do assembler, que traduz a linguagem Assembly para a linguagem de maquina.

### Conceitos básicos
- Por default as linguagens podem fazer todas operações básicas `+ - * /`, inclusive o módulo `%` (resto de uma divisão) muito usado para saber se um número é par ou não.
	- Em strings o operador `+` geralmente é usado para concatenação.
- Operadores matemáticos são muito usados na construção de programas.
- Operadores de comparação numérica como `< <= > >= == !=` são usados para avaliações em Loops e estruturas de controle.

**Variáveis** são lugares na memória onde um valor é armazenado, é algo que pode armazenar informações e pode ser referenciado e manipulado. Poder referenciar um valor que pode ser usado mais tarde é essencial para qualquer programa.

 A variável é um local na memória, o nome associado àquele local. Esses locais são usados pra armazenar dados, que serão posteriormente usados por programas. A diferença entre constantes e variáveis é a de que o valor associado ao nome da variável pode mudar durante a execução do programa.

É uma espécie de caixa de papelão, que tem um **tipo**, **nome** e um **dado** armazenado dentro dela. Toda vez que a execução termina essas caixas de variáveis são apagadas, e quando o programa é executado elas são criadas novamente.

**Tipos de dados** são diferentes tipos de dados que um programador pode usar. Cada linguagem tem seus tipos específicos, mas a grosso modo, em qualquer linguagem, eles seriam mais ou menos os seguintes.

```
inteiro (int) numero = 10
real (float, double) preco = 10.99
logico (bool) condicao = verdadeiro (ou falso)
texto (string) nome = "Joselito"
caractere (char) sexo = "M"
```

Os dados no computador são classificados em tipos, tendo uma representação única e precisam de quantidades variáveis de memória. Cada tipo tem diferentes operações que podem ser feitas com seus conjuntos de dados, por exemplo, números inteiros podem ser somados enquanto que caracteres não podem.

[Type Systems in Software Explained With Examples](https://thevaluable.dev/type-system-software-explained-example/)

A **inicialização** é o ato de definir o nome da variável e o tipo de dado que ela irá armazenar e faz com que um espaço na memória seja reservado para o conteúdo da variável, onde ficará armazenado. Uma variável pode ser criada sem valor dentro, seu conteúdo será `null`

A **atribuição** é o ato de definir o valor de uma variável, o que faz com que o valor seja copiado para a região de memória da variável, sobrescrevendo o que havia ali; essa operação pode ser feita inúmeras vezes durante a execução do programa.

Atribuição é conceitualmente muito simples. Você está armazenando um valor em algum armazenamento nomeado (variáveis): `inteiro a = 2` Aqui, o valor 2 está sendo armazenado em `a`, uma variável inteira. Você pode acessar o valor pelo nome que você deu ao seu armazenamento e também pode usá-lo para outras atribuições:
```
inteiro b = 3
b = b + a
```
- A coisa a lembrar é que `a` e `b` não são objetos, são nomes de caixas nas quais depositamos objetos.

As **convenções para nome** de variáveis geralmente envolvem nomes significativos e formas de escrever, como o camelCase.

Normalmente um programa prossegue de cima para baixo, linha por linha, executando cada instrução e passando para a próxima. Ele faz isso para sempre, até encontrar uma instrução que o diga para parar, ou um tipo de erro que o force a parar. Mas um programa que só pode prosseguir ou parar não pode fazer muita coisa realmente interessante. Os programas tornam-se verdadeiramente expressivos quando você tem uma maneira de alterar a ordem futura de execução com base em algum estado presente. Mecanismos que fazem isso são chamados de construções de fluxo de controle, que podem ser estruturas condicionais ou de repetição.

**Blocos** são essas coisas envoltas por `{ }`. A área de influência de um bloco, incluindo o armazenamento que possui e o armazenamento que pode acessar, é chamada de **escopo**. Escopos definem restrições de acessibilidade que uma variável possuem no código; pode ser global e acessível em todo código, ou local, sendo acessível apenas dentro de classes, funções ou blocos de códigos.

**Função** é um bloco que tem um nome e que pode ser invocado de outro lugar (quando inputs são passados para ele) são chamados de funções. Função é um segmento de código que pode ser executado facilmente por chamar o nome da função (abstraindo várias operação em uma única linha, quando a função é chamada). Podem ser chamadas inúmeras vezes e em qualquer parte do código. Elas podem ser com argumentos ou sem argumentos retornando ou não valores.

**Estruturas condicionais** são declarações que alteram o caminho do código dependendo de certas condições. Um programa sem instruções condicionais faria o mesmo sempre, o que o tornaria inútil. Em geral essas estruturas são `if...else if...else` e `switch case`.

**Estruturas de repetição** (ou loop) são estruturas que repetem um bloco de código enquanto/até que determinado resultado seja atingido. Em geral essas estruturas são o `for`, `while` e `do...while`.

É absolutamente essencial ter uma compreensão intuitiva sobre **indireção** e **recursão**. Esse talvez seja o fator mais importante que distingue um programador desajeitado de um habilidoso. A indireção e a recursão são mais difíceis no início do que o armazenamento e o fluxo porque seu uso forma estruturas gráficas conceituais que você deve ser capaz de ver em sua cabeça a fim de manipular e percorrer.

**Recursão** é a ideia de uma função chamando a si mesma, efetuando a execução repetida sequencial de uma maneira não muito diferente de um loop. O uso inteligente da recursão permite iterar de maneiras muito mais complexas do que um simples loop. É muito mais fácil, por exemplo, subdividir continuamente um grupo para realizar alguma tarefa nos subconjuntos com recursão do que com loop. Vários meios de ordenar coleções, ou procurar itens em hierarquias aninhadas complicadas, são naturalmente adequados para serem subdivididos ou acumulados dessa maneira recursiva.

Lembre-se, a regra de ouro é conhecer o básico tão bem que você mude do pensamento consciente para a ação reflexa. Pode se levar que leve muito tempo para internalizar esses conceitos depois de tê-los aprendido. Para que isso aconteça, não há atalho a não ser a exposição repetida.

### Interpretação e Compilação
A Eletrônica manipula a eletricidade através de dois estados: verdadeiro e falso, 0s e 1s. Um bit é o um ou o zero armazenado, o conjunto de 8 bits forma um byte.

Em linguagens de alto nível as instruções são de uma tal forma que permitem que pessoas controlem a execução de um computador, manipulando os dados. Essas instruções formam o **código fonte**, que deverá ser convertido em **linguagem de máquina**, a única coisa que computadores manipulam e entendem realmente (uma longa cadeia de 0s e 1s que manipulam a eletricidade).

Essa conversão pode ocorrer por **compilação**, quando todo o bloco de instruções do código fonte é convertido de uma vez, ou por **interpretação**, quando pedaços e instruções individuais são convertidos por vez, conforme a necessidade. 
- A **compilação** executa um programa de forma mais eficiente e rápida, verifica erros antes de executar mas demandam um tempo maior para executar e o fazem em apenas uma arquitetura de máquina (que funciona com aquele compilador).
- Já a **interpretação**, por mais que mais lenta e verificar erros enquanto executa, em seu desenvolvimento começa a executar na hora e o pode fazer isso em máquinas com arquiteturas diferentes.

Uma mesma linguagem pode ser interpretada e compilada, e isso depende das ferramentas que ela possuí e qual você usa para fazer essa conversão. Outras ainda podem ter um **modelo híbrido**, pegando o melhor de ambos os mundos.
- Uma dessas é o JIT Compilation (just in time compilation), compilação na hora certa, usado no moto v8 do JavaScript.
- Já no caso do Java, primeiro o código é compilado para uma linguagem intermediária, chamada byte code, que independe da plataforma específica em que foi gerado, para depois poder ser executado pela interpretação na Máquina Virtual Java (JVM). Isso permite que o mesmo código rode em várias plataformas de hardware diferentes.

[The Differences Between Interpreter and Compiler Explained](https://thevaluable.dev/difference-between-compiler-interpreter/)

Também podemos classificar uma linguagem de programação pelo seu nível de semelhança com a linguagem de máquina.
- Linguagens de **baixo nível** (Assembly e C) estão mais próximas do binário do que as de mais alto nível, dessa forma estando mais próximos das instruções que a máquina pode compreender.
- Já outras estão mais próximas da forma que os humanos pensam (Java e Python), e dessa forma, mais longe da linguagem binária, portanto de **alto nível** (a linguagem de implementação primária para linguagens de alto nível é C)

Linguagens muitas vezes são especializadas para determinadas tarefas, embora existam as de uso geral.

### Assembly
Linguagens de programação são um conjunto de técnicas fornecidas para o benefício do programador humano. Mas para executá-los, eles devem ser compilados em código de máquina, que nada mais é do que uma longa sequência de dígitos binários. interpretar esses fluxos de números é notoriamente difícil para os humanos, embora não impossível.

Linguagem de baixo nível, escrita em mnemonicos que refletem de perto as operações de uma CPU. Em português seria algo como _linguagem de montagem_. A linguagem assembly é um conjunto de mnemônicos legíveis por humanos para código de máquina, além de um punhado de atalhos simples que economizam trabalho. Assembly foi uma das primeiras invenções para tornar a programação mais eficiente para operadores humanos, antes dos compiladores e antes das linguagens de alto nível. 

Exemplos em assembly são suficientes para demonstrar o que realmente está acontecendo por baixo do código, a fim de desenvolver intuições sobre o que é possível em computadores e para desenvolver mais flexibilidade na adaptação a novos sistemas.

> _Eu acredito firmemente que todo programador de alto nível que se preze precisa entender C, e todo programador C precisa entender Assembly. Os medíocres mergulham em sua abstração e fazem carreira só dela, fechando os olhos para qualquer coisa fora de seu jardim murado. Mas para realmente ser bom, você precisa saber o que está acontecendo sob seus pés._ [how I think when I think about programming - alice maz](https://www.alicemaz.com/writing/program.html)

### Sintaxe e Semântica
É recomendável que aprenda as regras e sintaxe de uma linguagem antes que comece a escrever programas complexos. A maioria dessa regras são tediosas, porém fáceis de dominar. A sintaxe de uma linguagem é o conjunto de regras que devem ser seguidas no uso da linguagem (o que conhecemos como gramática) se quisermos que o programa funcione corretamente. Cada linguagem tem uma sintaxe própria, embora possam ter coisas em comum.

Ignorar essas regras resultará em erro no programa. Se esquecer um `;` no final de uma instrução ou esquecer uma letra, o programa inteiro não irá executar. Por exemplo, para que uma instrução `if` seja sintaticamente correta, você precisará de:
- Uma condição.
- Alguns parênteses.
- Alguns colchetes.

```js
if(var > 0){
	console.log("Positivo");
}
```

A semântica, por outro lado, é o significado por trás das construções. Por exemplo, a semântica de uma instrução `if` pode ser explicada da seguinte forma:
- A condição é executada.
- Se a condição for verdadeira, o corpo da instrução é executado.
- Se a condição for falsa, o corpo da instrução não será executado.
- A execução continua.

Por que precisamos de sintaxe e semântica? Destina-se a se comunicar com dois tipos diferentes de entidades:
- Seus colegas desenvolvedores precisam entender o que você fez.
- O computador precisa “entender” as instruções para executá-las.

### Tipagens
- **Tipagem dinâmica**: em uma linguagem de tipagem dinâmica, você não precisa **declarar o tipo de dado que será armazenado na variável**, trazendo uma maior flexibilidade na escrita do código.
- **Tipagem estática**: em linguagens de tipagem estática, **é obrigatório a declaração do tipo de dado que a variável irá receber, antes de atribuir valor a ela**, e depois de atribuído o tipo de dado a variável sempre será daquele tipo. Concede uma maior segurança ao código ao custo de maior enrijecimento em sua escrita.
- **Fortemente tipado**: em linguagens fortemente tipadas, as operações entre valores de tipos diferentes resultará em erros, portanto essas operações dar-se-a apenas por valores do mesmo tipo ou através da conversão (casting) de valores.
- **Fracamente tipado:** em linguagens fracamente tipadas, as variáveis declaradas, poderão intercambiar seus tipos a qualquer momento, ou seja, poderão receber valores de tipos de dados diferentes e fazer operações entre eles sem a necessidade de um conversão (casting) explicita do tipo.

### Aprendizagem
Programação não é nada de especial, é uma forma de manipulação de símbolos abstratos aplicados. Linguagens de programação diferentes fazem as mesmas coisas de maneiras diferentes e, uma vez que você fique bom, você pode se mover com fluidez entre elas.

A única razão pela qual a programação é tão comumente autodidata é porque é um sistema que é extraordinariamente adequado de ser compreendido pela tentativa e erro e por pessoas sem conhecimento especializado ou equipamento especializado. Uma vez que você domina seu estilo de aprendizagem, desde que você seja brilhante, curioso e determinado, você pode aprender qualquer coisa.

Escolha uma linguagem de programação e fique com ele até que você esteja pelo menos em um nível intermediário. Depois disso ramifique para outras linguagens diferentes.
- Quando você conhece um idioma, você pensa em termos desse idioma. Uma vez que você conhece vários em um paradigma, você pensa em termos do paradigma. Uma vez que você conhece os paradigmas, você pode simplesmente pensar em programação. Você precisa ser capaz de relacionar ativamente o material através das lacunas conceituais, ou ficará preso nesses containers especializados.
- Javascript e Python são provavelmente as linguagens para iniciantes mais razoáveis. Ambas têm suas peculiaridades, mas têm uma riqueza de material de aprendizado e, mais importante, suporte abrangente de biblioteca para qualquer coisa que você queira fazer.

A melhor maneira de aprender a programar, é criar um pequeno projeto que pareça tratável e descobrir o que você precisa para resolvê-lo. isso é mais fácil dizer do que fazer, porque os novos programadores têm mais dificuldade do que qualquer um para pensar em coisas para tentar e em julgar se são factíveis. Você quer construir algo que você goste, que faça você sentir que criou algo de valor, não importa quão bobo ou pequeno seja.

Catalogo o conhecimento como um gráfico gigante, esparramado, sem organização e interligado frouxamente em alguns lugares e firmemente em outros. Quando encontrar novos tópicos, nunca se preocupe se não entender a maior parte. Apenas procure maneiras de relacioná-lo com seu gráfico. Se ler um texto fora da sua profundidade e mal o entender, ele ainda estabelecerá as bases (uma estrutura esquelética) que mais tarde pode ser desenvolvida com mais material.

Quanto mais apertado você torna o ciclo de feedback-resposta, mais rápido você pode trabalhar, mais rápido você pode pensar, mais natural e sem esforço tudo parece.

---
Para ampliar a compreensão:
- [[Arquitetura de Computadores]]
- [[Estrutura de Dados e Algoritmos]]