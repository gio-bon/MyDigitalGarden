---
title : Linux
---

- Usuários
	- `passwd` muda senha usuário atual, para root `sudo passwd`
	- Para logar/alternar como outro usuário -> `su <nome usuario>`
	- Para criar usuário novo -> `adduser <nome>` -> pede senha e outros dados
		- `chmod o-rx <usuário>` para evitar que os outros usuários tenham acesso aos dados deste usuário (ara alterar a permissão da pasta você deve estar logado com o usuário)
- `which firefox` localiza o caminho do arquivo de onde o programa é executado
- Variáveis de ambiente e PATH
	- A saída lista todas as variáveis de ambiente que o seu sistema possui -> `env`
	- As variáveis de ambiente são variáveis globais que podemos utilizar para definir configurações, personalizar nosso terminal.
	- Quando executamos o comando env, podemos ver quais são as variáveis que estão definidas. A variável HOME, por exemplo, guarda o caminho para o diretório do usuário.
	- A variável PATH, guarda informações de onde estão nossos arquivos executáveis para que possamos executar um comando sem a necessidade de digitar o caminho absoluto.
	- `PATH=$PATH:/home/giovani/pasta-tal` adicionando ao PATH esse diretório (o que houver lá dentro será acessível diretamente)
		- É necessário colocar essa instrução em `.bashrc` para que a mudança persista (senão, a alteração só vale para aquela seção)
- Contar a quantidade de palavras em arquivos
	- `wc -w *.txt`
	- Além de contar o número de palavras em um arquivo, o comando `wc` pode também contar o número de caracteres e linhas em um arquivo, ou em uma saída do terminal. Para isso, podemos utilizar a opção `-c` para caracteres e `-l` para linhas.
	- Se utilizarmos o comando `ps -e`, que lista todos os processos, podemos passar o retorno do `ps` para o `wc -l` contar quantas linhas o retorno possui. A quantidade de linhas representa a quantidade de processos existentes no nosso sistema.
		- `ps -e | wc -l`
- Instalações
	- APT (ubuntu)
		- Pesquisa -> `apt-cache search <nome programa>`
		- Instalar -> `sudo apt-get install <nome programa>`
		- Desinstalar -> `sudo apt-get remove <nome programa>`
		- Para atualizar a lista de pacote que estão disponíveis para instalação -> `apt-get update`
		- Atualizando as versões dos pacotes que já estão instalados -> `apt-get upgrade`
	- dpkg (debian)
		- Instalar -> `sudo dpkg -i <nome pacote>`
			- `sudo dpkg -i google-chrome-stable_current_amd64.deb`
		- Desinstalar -> `sudo dpkg -r  <nome pacote> `
			- `sudo dpkg -r google-chrome-stable`
	- Código fonte
		- Baixar código fonte, geralmente em `.tar.gz`
		- Depois de descompactar, buscar arquivo `./configure` que rodará script pra ver se tem as dependências
		- `make`, ainda podem faltar dependências, que podem ser buscadas com `apt-cache search <nome programa>`
		- `sudo make install`
- Serviços
	- Os _scripts_ dentro do diretório `/etc/init.d` serão executados quando nosso sistema inicia. Esses scripts são escritos para suportar opções como `stop` e `start`. Utilize o comando `ls /etc/init.d/` e veja quais serviços o seu computador possui.
	- `sudo service <nome> stop`
	- `sudo service <nome> start`
- Acesso a servidor remoto do linux com SSH
	- Instalação
		- Cliente: `sudo apt-get install ssh-client` (eu conectando em outros)
		- Servidor: `sudo apt-get install ssh-server` (outros conectando no meu pc)
		- Ambos com `sudo apt-get install ssh`
	- Acesso
		- Terminal -> `ssh user@localhost`
		- Modo gráfico -> `ssh -X user@localhost`
	- Mandar arquivo do meu pc pra remoto -> `scp arq.zip jose@localhost:/home/jose`

## Comandos Básicos
- Saber nome de usuário -> `whoami`
- `man` para consultar o manual sobre determinado comando.
	- `man ls`
- Informa o diretório atual -> `pwd`
  card-last-score:: 1
  card-repeats:: 1
  card-next-schedule:: 2022-01-23T03:00:00.000Z
  card-last-interval:: -1
  card-ease-factor:: 2.5
  card-last-reviewed:: 2022-01-22T19:10:17.660Z
	- `/home/guilherme`
- Mudar de diretório  cd`
	- Volta com `cd ..`
	- `cd NomePasta`
- Modifica os dados de um arquivo para a data e hora atual -> `touch`
```bash
drwxr-xr-x  4 gio  gio      4096 jan 22 13:36 'Área de Trabalho'
-rw-rw-r--  1 gio  gio        25 jan 22 16:21  arq1.txt
-rw-rw-r--  1 gio  gio        25 jan 22 16:22  arq2.txt
	  
touch arq1.txt   //modifica para a data atual
```
- Lista os arquivos e diretórios `ls`
	- `ls -la`, lista além dos arquivos e diretórios ocultos
	- `ls -l` lista informações extras sobre cada arquivo (tamanhos, datas de modificação e os tipos)
	- Pode ser usado para ver arquivos de outro diretório com `ls <caminho>`
- Permissões em `ls -l`
	- Quando encontramos um `-` significa que não temos uma determinada permissão
	- Para alterar permissões -> comando `chmod`
- `locate` para encontrar os locais de arquivos no sistema
```
$ locate fazbackup    
/home/giovani/scripts/fazbackup
```
- Para atualizar a base de dados que o locate utiliza para realizar as pesquisas -> `sudo updatedb`
- Printa texto no terminal `echo`
	- Para inserir texto dentro de um arquivo
		- `echo "Oasis" > musicas-favoritas.txt`
		- `echo "Noel Gallagher" >> musicas-favoritas.txt` para inserir nova linha em arquivo já existente.
- Lê arquivos no terminal -> `cat`
	- `cat musicas-favoritas.txt`
	- Lê todos os arquivos com o padrão
		- `cat arq*.txt` ou `cat arq?.txt` vai abrir arquivos como `arq1.txt` `arq2.txt` ...
		- `cat *.txt` abre por extensão
- Ler arquivos de texto com `head` `tail` e `less`
```bash
head google.txt  //no comeco do arquivo
head -n 3 google.txt  //especificando número de linhas
	  
tail google.txt  //no fim do arquivo
tail -n 3 google.txt  //especificando número de linhas
	  
//nos permite abrir e navegar pelo texto do arquivo no Terminal utilizando as setas para cima e para baixo do teclado
less google.txt
```
- Cria pastas `mkdir`
	- `mkdir workspace`
- Remove arquivos ou pastas ->  `rmdir` `rm`
```bash
rmdir projetos-java
rm arquivo3.txt
```
- Remover pasta quando ela tem coisas dentro: `rm -r workspace/` -> `-r` como parâmetro recursivo
- Cópia de arquivos e diretórios com  `cp`
	- Arquivo `cp original.txt novo.txt`
	- Diretório `cp -r projetos-java projetos-c#`
- Mover ou renomear arquivo com `mv`
	- Renomeando -> `mv bemvindo.txt projetos-java/`
	- Mover e mudar nome -> `mv bemvindo.txt projetos-java/bemvindo-novo-nome.txt`
- Compactar e descompactar arquivos com `zip` e `unzip`
	- Compactando: `zip -r work.zip workspace/` como `zip -r <arquivo-a-ser-criado.zip> <pasta-a-ser-compactada/`
	- Descompactando: `unzip work.zip`
		- Observar quais arquivos e diretórios foram compactados com `unzip -l work.zip`
- Compactar e descompactar arquivos com `tar`
	- Compactar
		- `tar -cz workspace > work.tar.gz`
		- `tar -czf work.tar.gz workspace/` sem setas
	- Descompactar
		- `tar -xz < work.tar.gz`
		- `tar -xzf work.tar.gz` sem setas
	- O comando tar não compacta, apenas empacota os arquivos, usando outros compactadores. Acima foi usado no formato `.gz`, pelo compactador `gzip`. Abaixo o processo feito com o `bzip2` > `.tar.bz2` (mais eficiente e mais lento também)
		- `tar -cjf work.tar.bz2` => muda o `-z` para `-j`

## Processos
- `ps` lista de forma simples os processos do terminal apenas
```
PID TTY          TIME CMD
1 ?        00:00:00 systemd
2 ?        00:00:00 kthreadd
3 ?        00:00:00 rcu_gp
```
- `ps -e` lista de forma simples todos os processos do sistema
- `ps -ef` lista de forma simples todos os processos do sistema com mais detalhes
```
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 12:57 ?        00:00:00 /sbin/init splash
root           2       0  0 12:57 ?        00:00:00 [kthreadd]
root           3       2  0 12:57 ?        00:00:00 [rcu_gp]
root           4       2  0 12:57 ?        00:00:00 [rcu_par_gp]
```
- `kill <PID>` para encerrar processo de forma que ele possa realizar algumas tarefas antes de ser encerrado (equivale a `$ kill -TERM 11269`)
	- `kill -9 10092` mata o processo de forma forçada
- Mata todos os processos com um determinado nome -> `killall firefox`
	- `killall -9 firefox`
- Mostrar consumo de CPU e memória com `top` (atualizado de tempos em tempos e classificados do mais pro menos) => para mais informações do comando `man top`
	- `top -u lucas` para os dados de apenas um usuário
	- `top -p 19509` para informações de processo específico
	- Por padrão, o `top` atualiza a tela com novas informações sobre os processos a cada 3 segundos. Para alterar esse tempo basta pressionar `d` enquanto estiver rodando o `top`, inserir o valor desejado e pressionar a tecla `Enter`:
- Redirecionar a saída de processos e mostrar as linhas que possuem determinado termo -> `ps -ef | grep firefox`
	- Também dá pra fazer com arquivos -> `cat processos.txt| grep "Logseq"`
- Para visualizar essa árvore de processos -> `pstree`
- Abrindo um programa no terminal ele trava/ocupa o terminal, para pausar sua execução e liberar o terminal `ctrl + z`.
	- Com `jobs` é possível saber os processos que rodam em background `bg` e foreground `fg`
	- Para colocar o processo 1 (visto com `jobs`) em background e vice-versa -> `bg 1` e `fg 1`

## Scripts
- Ao criar um arquivo com instruções dentro é possível executá-lo com `sh nome-arq` o por lhe dar permissão de execução com `chmod +x nome-arq` e depois o executar com `./nome-arq` estando no mesmo diretório.
	- Assim como temos o `+x` para adicionar permissão de execução, temos também o `+r` e o `+w`. Podemos também combinar essas permissões da seguinte forma: `chmod +rwx`.
- O `~` em `~/workspace/` é um atalho para representar o diretório do usuário. Sempre que quisermos nos referir ao diretório do usuário (`/home/nome_do_usuario/`), podemos utilizar o `~`. Dessa forma independente de qual seja o nosso diretório atual, o comando saberá onde o diretório `workspace` se encontra.

## VI
- Abre arquivos com `vi arquivo.txt`
- Modo de edição com `i`
	- Excluí um caractere com `x` -> `11x` tira 11 caracteres
- Modo de visualização com `esc`
	- Excluí uma linha com `dd`
	- Para pesquisas com `/` e digite o termo desejado
		- `n` para ir para a próxima ocorrência
	- `0` vai para o começo da linha a atual e `$`para o fim
	- `yy` para copiar linha e `p` para colar
		- `3yy` para copiar 3 linhas e `p` para colar
		- `10p` cola 10x o mesmo conteúdo
	- `1... + shift g` vai para o começo da linha selecionada, nesse caso a linha 1
	- `shift n` volta pra linha anterior
	- `shift g` vai para o começo da linha
- Para salvar `:w` e para sair `:q` -> `:wq`
	- Sair sem salvar com `:q!`