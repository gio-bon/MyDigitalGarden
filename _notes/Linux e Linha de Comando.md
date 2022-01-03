---
title: Linux e Linha de Comando
---

Trabalhar com a linha de comando é uma habilidade crítica para você aprender como desenvolvedor. A linha de comando é como nossa base de operações, a partir da qual podemos lançar outros programas e interagir com eles. Ela tem uma sintaxe própria para aprender, mas como você estará entrando nos mesmos comandos dezenas de vezes, você rapidamente pegará os comandos que mais precisa. Além disso, você estará usando principalmente o [[Git e Github]] dentro da linha de comando.

## Linha de comando
E uma época em que não havia interface gráfica, a única forma de interagir com um computador era por linha de comando. O Bash está um nível acima do SO -> Kernel -> Hardware.

### Comandos
A síntaxe de um comando: `<comando> <opções>`

### Opções
Em geral, as `<opções>` consistem em uma única letra, precedida por um hífen. Mas você pode agrupar opções de uma letra ou preceder cada uma com um hífen, para usar mais de uma opção de cada vez.

Abaixo, em ambos os casos o comando `ls` é executado com as opções `-l` (listagem longa) `-a` (exibe arquivos de ponto ocultos) e `-t` (lista por tempo).

`ls -l -a -t`
`ls -lat/`

Alguns comandos incluem opções que são representados por uma palavra inteira. Para instruir um comando a usar uma palavra inteira como uma opção, você geralmente a precede com um hífen duplo => `ls --help`

### Argumentos
Um argumento é um fragmento extra de informações, como um nome de arquivo, diretório, nome de usuário, dispositivo ou outro item que informa ao comando o objeto sobre o qual ele deve atuar.

`cat /etc/passwd` -> exibe o conteúdo do arquivo `/etc/passwd` em sua tela

## Comandos de navegação
- **Path absoluto**, ou caminho absoluto, é o path cujo início é a raiz do sistema, ou seja, o diretório `/`. -> `cd /diretorio`
- **Path relativo**, ou caminho relativo, é aquele que o início é o diretório corrente, ou seja, não precisamos informar o caminho a partir do `/`. -> `cd diretorio`

- `cd..` diretório acima
- `cd` ou `cd ~` navegaremos até a home de nosso usuário
- `cd -`  retorna para o último diretório acessado 
- `cd /diretorio` partindo da raiz até o último diretório passado como referência
- `cd diretorio` parte do local corrente até o diretório passado como referência
- `pwd` *print working directory*, que nos informa o diretório corrente, apresentando o caminho desde o diretório raiz até o atual.
- `ls` podemos visualizar o conteúdo de um diretório e também informações sobre arquivos, informando dados como nomes de arquivos, permissões, proprietários e datas de criação, além de inúmeras opções para exibir as informações de diversas formas.
- `ls -a` mostra todos os arquivos, incluindo os ocultos.
- `ls -A` semelhante ao `-a`, mas não mostra o diretório corrente (`.`) ou o diretório acima (`..`).
- `ls -i` mostra o número do inode de cada arquivo na primeira coluna. 
- `ls -l` formato longo, mostra permissões, número de links, propietário, grupo, tamanho, data de modificação e nome do arquivo.

### Comandos para arquivos e pastas
- `df`  mostra o espaço livre/ocupado de cada partição. Pode ser utilizado junto com várias opções, se for utilizado sozinho, mostrará o espaço usado e disponível de todos os sistemas de arquivos atualmente montados.
- `df -h` mostra o espaço livre/ocupado em MB, KB, GB em vez de bloco.
- `df -k` lista em Kbyts.
- `df -m` lista em Mbytes.
- `cat` derivação da palavra concatenate, permite que a gente crie, una e exiba arquivos no formato padrão de tela ou em outro arquivo, entre outras funcionalidades.
- `cat -E` marca o término de linha mostrando o caractere **$** ao final de cada uma delas.
- `cat -n` mostra a quantidade de linas do arquivo]
- `cat -b` numera as linhas que possuem algum conteúdo.
- `mkdir` é um acrônimo para *make directory*, ele cria novos diretórios em um sistema de arquivos => `mkdir Exemplo` 
	- Este comando também nos permite criar vários diretórios ao mesmo tempo somente passando o nome dos diretórios seguidos um do outro => `mkdir Exemplo2 Exemplo3 Exemplo4`
	- Ele também permite criar uma estrutura de arquivos usando esse mesmo comando passando a opção `-p` => `mkdir -p Exemplo4/Exemplo5/Exemplo6`
- `touch` é muito utilizado para criarmos arquivos vazios porém ele também é capaz de alterar o registro de data e hora de arquivos e pastas.
	- Vamos criar um arquivo vazio usando o comando `touch` => `touch exemplo1.txt`
	- Este comando também nos permite criar múltiplos arquivos somente passando o nome dos arquivos em seguida um do outro => `touch exemplo2.txt  exemplo3.txt`
	- Podemos gerar nomes automáticos usando as chaves `{}` enquanto criamos varios arquivos desta maneira => `touch exemplo{4..6}.txt`, este comando irá criar 3 arquivos chamados exemplo4.txt, exemplo5.txt e exemplo6.txt.
- `cp` nos permite copiar arquivos ou diretórios para outro local.
	- para copiar um arquivo => `cp exemplo1.txt exemplo2.txt`
	- Para copiarmos um diretório nós adicionamos a opção `-r` => `cp -r Exemplo/ Exemplo2/`
- `mv`para movermos ou renomearmos um aquivo ou um diretório.
	- Movendo um diretório para dentro de outro => `mv Exemplo2 Exemplo`
	- Movendo um arquivo para dentro de um diretório => `mv exemplo1.txt Exemplo/Exemplo2/`
	- Renomeando um diretório =>`mv Exemplo/Exemplo2/ Exemplo/Linux`
	- Renomeando um arquivo => `mv exemplo2.txt He4rtDevs.txt `
- `rm` nos possibilita excluir diretórios vazios, não vazios e arquivos.
	- Excluindo arquivos => `rm He4rtDevs.txt`
	- Para excluirmos diretórios nós passamos a opção `-r` => `rm -r Exemplo/`

## Script
Para criar e executar scripts:
- Após você copiar o código que você pretende executar, crie um arquivo .sh e coloque este conteúdo: `nano nome_do_arquivo.sh`
- Depois colar todo o código e salvar este arquivo usando o comando CTRL + O, dê a permissão de escrita: `chmod +x nome_do_arquivo.sh`
- Por ultimo você poderá executar o arquivo utilizando **./**: `./nome_do_arquivo.sh`

Obs: a primeira linha do script deve ter `#! /bin/bash`

Veja [[Bash]]

---

- [LucasHe4rt/linux4noobs: Tutorial De Linux para iniciantes em Programação.](https://github.com/lucashe4rt/linux4noobs)
- [O que é Shell e qual sua função? | Segredo Dev](https://segredo.dev/o-que-e-shell/#como-o-shell-funciona)
- [GuiaFoca — Site Oficial do GuiaFoca](https://guiafoca.org/)
- [explainshell.com - match command-line arguments to their help text](https://explainshell.com/)