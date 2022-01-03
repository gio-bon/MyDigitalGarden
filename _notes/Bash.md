---
title: Bash
---

## Variáveis
``` bash
  #! /bin/bash
  NAME="HE4RT" => deve estar tudo junto
  echo $NAME
```
- SEMPRE que formos acessar uma variável, é necessário utilizar o `$` antes da variável.
- Um nome de variável DEVE ser feito em UPPER CASE e é considerado boa prática (é case-sensitive)
- Não use espaços depois da inicialização de uma variável e seu valor.
- Não utilize palavras reservadas como nome de variável (if, else, for, while, int, float, etc.)
- Não use nome de variáveis com espaço.

## Entrada e saída

### echo
- A função echo repete o que você diz para repetir (realmente como se fosse eco).
- Esta função, diferente de algumas linguagens, pode imprimir qualquer tipo, ou até mesmo ser chamada sem parámetro nenhum, imprimindo assim uma linha vazia.
- Caractere de escape => `\`
- Não precisa de aspas simples ou duplas, mas é bom ter

### printf
A função `printf` é exatamente similar ao printf do C. Portanto, tambem é necessário passar o formato do argumento na string a ser impressa e posteriormente os parâmetros, como podemos ver melhor abaixo:

``` bash
#! /bin/bash

printf "Número de vagas Vazias: %s" "34"
printf "Número de vagas Ocupadas: %s" "16"
```

### read
A função `read` para a execução do programa até o usuário escrever um argumento. Após o usuário escrever o argumento, esse resultado (por padrão) será armazenado em uma variável de nome `REPLY`.

``` bash
#! /bin/bash
echo "Qual o seu Nome?"
read
echo "Olá, ${REPLY}. Seja bem-vindo ao curso de Bash"
```

Caso não queira salvar o output do reply na variável `REPLY`, é possível adicionar um parâmetro que será o nome da variável que a entrada será armazenada

``` bash
#! /bin/bash
echo "Qual o seu Nome?"
read NAME
echo "Olá, ${NAME}. Seja bem-vindo ao curso de Bash"
```

## Operadores 
### Aritméticos
Existe duas formas de utilizar esses comandos, usando `expr` e `$((Operador))`

``` bash
echo `expr 3 + 2`
echo $((3+2))
```

``` bash
echo `expr 3 - 2`
echo $((3-2))
```

``` bash
echo `expr 3 \* 2`
echo $((3*2))
```

``` bash
echo `expr 4 / 2`
echo $((4 / 2))
```

``` bash
echo `expr 3 % 2`  #módulo (resto da divisão)
echo $((3%2))
```

``` bash
echo $((3**2))   #exponenciação
```

### Lógicos
- NOT => `!`
- AND => `&&`
- OR `||`

### Comparação

| Operadores de Comparação | Significado |
|---|---|
| > | maior que |
| < | menor que |
| >= | maior ou igual |
| <= | menor ou igual |
| == | igual |
| != | não igual (diferente) |
| =~ | checa padrão |
Outras comparação

| Operadores de Comparação | Significado |
|---|---|
| -gt | maior que |
| -lt | menor que |
| -ge | maior ou igual |
| -le | menor ou igual |
| -eq | equivalente/igual |
| -ne | não igual (diferente) |
| -d | arquivo é diretório |
| -e | arquivo existe |
| -z | arquivo vazio |
| -f | arquivo contém texto |
| -o | usuário é dono do arquivo |
| -r | arquivo pode ser lido |
| -w | arquivo pode ser alterado |
| -x | arquivo pode ser executado |

## Condicionais
### `if` `elif` `else`

``` bash
if [ CONDICAO ];
then
# SE SATISFAZ ENTRA AQUI
else
# SE NAO SATISFAZ ENTRA AQUI
fi
```

``` bash
if [ CONDICAO ];
then
# SE SATISFAZ ENTRA AQUI
elif [ OUTRA CONDICAO ];
then
# SE SATISFAZ ENTRA AQUI
else
# SE NAO SATISFAZ ENTRA AQUI
fi
```

Exemplo

``` bash
#! /bin/bash

DINHEIRO=100
VALOR=120

if [ $DINHEIRO -ge $VALOR ]; then
  echo "Você acabou de adquirir um fone de ouvido novo"
elif [ $DINHEIRO -le $VALOR ]; then
  echo "Você não tem dinheiro, seu pobretão"
else
  echo "Ainda outra opção"
fi
```

### `case ... in`

``` bash
#! /bin/bash

VARIAVEL=dois

case $VARIAVEL in
  1) echo "um" ;;
  dois) echo "2" ;;
  tres) echo "3" ;;
  quatro) echo "4" ;;
  5) echo "cinco" ;;
  6|SEIS|Seis|seis) echo "6" ;;
  sete) echo "7" ;;
  oito) echo "8" ;;
  nove) echo "9" ;;
  dez) echo "10" ;;
  *) echo "Opcao Invalida!" ;;
esac
```

## Repetição
### `while`

``` bash
#!/bin/bash

CONTROL=0

while [ $CONTROL -lt 10 ]
do
 echo $CONTROL
 CONTROL=`expr $CONTROL + 1`
done
```

### `for`

``` bash
VAR=0

for VAR in 0 1 2 3 4 5 6 7 8 9
do
 echo $VAR
done
```

Também é possível usar o `for` com uma sintaxe semelhante a do C.

```bash
#! /bin/bash

for ((i=0; i < 10; i++))
do
 echo $i
done
```

### `until`
O `until` é uma estrutura de loop que funciona de forma similar ao do while. Esta função irá verificar a condição e irá repitir o loop até que esta condição ocorra.

``` bash
#! /bin/bash

A=0

until [ ! $A -lt 10 ]
do
 echo $A
 A=`expr $A + 1`
done
```

### `select`
O `select` é uma estrutura de loop que funciona um pouco diferente das outras estruturas. Esta função em específico irá iterar cada objeto que está na lista.
``` bash
#! /bin/bash

select DRINK in tea cofee water juice appe all none
do
 echo $DRINK
done
```

## Controle de repetição
Tal como outras linguagens de programação, os comandos de repetição do bash possuem 2 palavras reservadas para controle de loop, sendo elas: `break` e `continue`.

A necessidade de utilização desses comandos se baseia conforme a necessidade do loop, e estes funcionam quase igual a outras linguagens de programação.
A diferença é que ambas podem receber parâmetros que indicam qual será o loop que será parado (no caso do break) ou que será continuado (no caso do continue).

``` bash
#!/bin/bash

A=0

while [ $A -lt 10 ]
do
  echo $A
  if [ $A -eq 5 ]
  then
	  break
  elif (($A == 1))
  then
	  echo "O Valor obtido é 1"
  fi
  A=`expr $A + 1`
done
```
```
  0
  1
  O Valor obtido é 1
  2
  3
  4
  5
```

``` bash
#!/bin/bash

NUMS="1 2 3 4 5 6 7"

for NUM in $NUMS
do
  Q=`expr $NUM % 2`
  if [ $Q -eq 0 ]
  then
	  echo "Número $NUM é par!!"
	  continue
  fi
  echo "Número $NUM é impar"
done
```
```
  Número 1 é impar
  Número 2 é par!!
  Número 3 é impar
  Número 4 é par!!
  Número 5 é impar
  Número 6 é par!!
  Número 7 é impar
```

``` bash
#!/bin/bash

for i in 1 2 3
do
  for j in 0 5
  do
	  if (($i==2 && j==0))
	  then
		  break 2
	  else
		  echo "$i $j"
	  fi
  done
done
```
```
  1 0
  1 5
```

## Variáveis especiais
O Bash possui algumas variáveis especiais que permitem você acessar informações do próprio sistema operacional dentro do código, além de acessar as variáveis de input de forma única.

Nesta tabela, você poderá encontrar e descobrir como utilizar algumas dessas variáveis no exemplo mais abaixo.

| Variáveis Especiais | Significado |
|---|---|
| $1 ... $n | Acessa os parâmetros de input do programa. $0 acessa o primeiro, $1 o segundo e assim em diante. |
| $IFS | Altera o separador do texto. Em vez de espaço pode ser o que você definir. |
| $@ | Imprime todos os parâmetros passados para a função. |
| $* | Tem o mesmo comportamento do $@ porém troca os espaços em branco por aspas duplas. |
| $# | Número de parâmetros que o script recebeu. |
| $0 | Nome do programa executado. |
| $! | Retorna o PID do último programa executado. |
| `$$` | Retorna o PID do processo sob o qual o script está sendo executado. |
| $? | Output do ultimo programa executado. |

## Funções

O bash permite que o usuário escreva suas próprias funções, também permitindo funções recursivas e não recursivas. Para construi-las é possível observarmos os exemplos abaixo.

``` bash
#!/bin/bash

myfunc()
{
echo "I was called as : $@"
x=2
}

Main script starts here

echo "Script was called with $@"
x=1
echo "x is $x"
myfunc 1 2 3
echo "x is $x"
```

- [ ] [Bash4Noobs/03-Arrays.md at main · DantasB/Bash4Noobs · GitHub](https://github.com/DantasB/Bash4Noobs/blob/main/src/4-Intermedi%C3%A1rio/03-Arrays.md)

---

[DantasB/Bash4Noobs: Tutorial de Bash para iniciantes](https://github.com/DantasB/Bash4Noobs)
[Online Bash Shell - online editor](https://www.onlinegdb.com/online_bash_shell)