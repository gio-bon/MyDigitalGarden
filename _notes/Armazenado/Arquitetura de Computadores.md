---
title : Arquitetura de Computadores
---

**Tipos de memórias**
- Memória não volátil e secundaria: hard disk e SSD, onde são armazenados os arquivos de um programa, onde são enviados, conforme a necessidade, para a memória RAM.
- Memória principal e volátil: RAM, para onde vão os dados que serão trabalhados pelo processador. É composta por vário endereços de acesso aleatório, em que em cada um deles fica armazenado um byte.
- A memória ROM é de apenas leitura e faz com que o computador inicie o sistema operacional inicialize e reconheça os dispositivos conectados.

O processador (CPU) acessa as instruções da memória RAM, as interpretará e fará operações com esses dados. É composto pela unidade de controle, que interpretará as instruções; a unidade lógico aritmética, que manipulará os dados;  e os registradores, onde ficarão guardados alguns resultados intermediário de operações no processador.
Assim há um fluxo constante de dados entrando no processador, sendo interpretados e manipulados, e devolvidos à memória RAM ou memórias não voláteis.

Sequência de passos do processador que se repete dentro de um clock (tempo específico para realizar um ciclo): 
  1. Buscar instrução
  2. Decodificar a instrução
  3. Execução da instrução

Em processadores de 3 GHz ocorrem 3 bilhões desses ciclos (busca, decodificação e execução) em um segundo. Basicamente, os computadores foram feitos para fazerem tarefas repetitivas, de acordo com a programação, muito rapidamente.

Para um programador, em um momento que for precisar ler uma grande quantidade de dados, deverá se atentar para a quantidade de memória RAM que será demandada pela tarefa. Isso pode ser abordado de uma forma eficiente para contornar o problema de falta de memória.

Para além de aumentar a velocidade de clock, a fim de melhorar o desempenho do processador (o que tem limitações, por se aumentar muito o processador superaquece), são usadas:
- **Pipelining** a técnica de pipeline, que é o encadeamento das instruções (enquanto uma instrução está decodificando a outra na sequência já está sendo buscada, ou seja, as coisas não precisam terminar completamente para que outras na sequência já comecem).
- **Multicore** processadores com mais de um core, executando as mesmas coisas em paralelo e de forma sincronizada.
- **Threads**, que significa dividir um mesmo core em dois ou mais pedaços lógicos que processam diferentes instruções ao mesmo tempo.

Os computadores tem **dispositivos de entrada e saída**. Como exemplo, e um monitor, é o driver do dispositivo que permite o processador imprimir na tela qualquer coisa que se queira, atendendo as especificações do hardware que se tem.
- Sistema de cores nos pixels do monitor: RGB.
- Placas de vídeo fazem os cálculos dos pixels e atualizações deles por segundo.
- Teclados funcionam atraves de posições numeradas (teclas) que mandam um sinal elétrico ao computador quando pressionadas. Essas posições são interpretadas por tabelas que representam essas posições como caracteres específicos.

**Multitarefa** é o termo que significa a ilusão que um computador cria de continuidade, de parecer fazer as coisas simultaneamente quando na verdade ele faz uma coisa de cada vez, intercalando vários processos (paralelismo) só que muitíssimo rápido. Assim o sistema operacional cria uma espécie de fila de processos e determina quanto tempo cada um deles vai ser executado, segundo certas prioridades.

Voltando para a questão das memórias, a memória RAM dinâmica (DRAM) é mais lenta para acesso de dados do processador, que é muito mais veloz. Pra resolver esse gargalo, é colocado pequenas memórias de RAM estática (ERAM) dentro dos processadores, que servem para dar acesso muito mais rápido aos dados que o processador está trabalhando no momento. Essas memórias dentro dos processadores são chamadas de **Cache**, e são muito mais caras que as RAMs dinâmicas. São divididas em níveis: L1 e L2 pra cada core, e a L3 para todos os cores.

Esse mesmo conceito de cache é usado em várias aplicações diferentes, desde a navegadores, programas e servidores (manter por perto o que pode e geralmente é usado com maior freqüência).

A hierarquia de memória leva em conta os fatores:
- custo de memória
- capacidade de armazenamento
- velocidade de acesso

Como hoje não é possível ter o melhor desses três itens em uma memória, é criada uma pirâmide de memórias que quanto mais se sobe, mais rápido é a velocidade e preço; quanto mais se desce, mais baratas e com maior capacidade de armazenamento. Cada tipo de memória na pirâmide conversa com a proxima camada, por exemplo, a memória RAM manda dados para a L3, a L3 para a L2 e assim por diante.

Princípio da localidade explica o porque de usar hierarquia memórias, pois temos a tendencia de acessar muito mais dados que estejam contidos em um pedaço específico da memória, além do fator temporal, que é a tendência de acessar mais dados gerados em um período de tempo próximo. Assim faz sentido possuir memórias muito rapidas para esses dados em uso e memorias maiores e mais lentas para dados pouco ou menos utilizados.

Computadores de 32 ou 64 bits significa a quantidade de bits de cada instrução nos registradores do processador. Os de 32 estao limitados ao o uso de memórias até 4GB, enquanto que os de 64 estao limitados a alguns bilhões de GB de RAM.

A representação de números em linguagens de programação é feita por sequência de bits, assim quantos mais bits para armazenar uma variável, maiores números poderão ser representados (números negativos tem 1 como primeiro bit, e os positivos 0).
Caracteres são mapeados em uma tabela, e o número escolhido para representar um caractere é usado em variáveis.

Para resolver o problema de incompatibilidade entre conjuntos de caracteres em línguas diferentes surge o Unicode. Mas por gastar dois bytes a mais para representar cada caractere, para computadores antigos isso significaria um gasto de memória inútil, pois iria gastar muito mais armazenamento (e gerando diversos problemas) só para fazer o que já era feito muito bem com o ASCII, por exemplo.

Surge o UTF-8 pra resolver esse problema, pois os caracteres tem tamanhos variados, com os ASCII gastando os mesmos 1 byte, e outros caracteres, como o chinês, gastando 3 bytes.

O contexto de execução de algo no computador vai determinar a interpretação dos bits, se são um número, caractere ou um pixel de imagem.

Ponteiros em listas fazem referência a um dado na memória, assim como um índice em um dicionário referencia certa informação. Melhora o desempenho porque evitam a copia de dados repetidas na memória. Isso dá lugar ao conceito de passagem de variáveis por referência e por valor.

Numero de ponto flutuante representa números muito grandes em notação científica, o que leva a poder representar números enormes com poucos bits e facilita nas contas. Mas essa representação não consegue representar tudo, algumas coisas são arredondada além de usar a base 2 para a exponenciação, e nao a base 10.

Podemos representar números muito grandes usando a representação de ponto flutuante. Essa representação tem um grande ganho em eficiência mas causa erros de arredondamento.

Já outra linguagens podem representar números gigantescos, como dois elevado a mil, sem erros de arredondamento, isso tudo por causa dos Inteiros de precisão arbitrária (BigInteger ou Bignum)

Nem todas as aplicações precisam de tamanha precisão (que tem o custo de muito poder computacional pra calcular), assim, algumas usam o número de ponto flutuante e outras os inteiros de precisão arbitrária (para maior precisão).