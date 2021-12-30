---
title: Git e Github
---

Instalação (ubuntu) e configuração de seus dados no git:

```bash
sudo apt-get install git
git config --global user.name "Fulano de Tal"
git config --global user.email "email@gmail.com"
```

## Funcionamento interno
### SHA1
Algoritmo de Hash seguro (encriptação) que gera um conjunto único de caracteres de 40 dígitos gerados a cada mudança do arquivo.

``` bash
❯ echo "texto a ser encriptado" | openssl sha1
(stdin)= 083891065fbc06f81b11eeb768617e2177c4c7d7
```

A chave muda conforme o aquivo é alterado.
``` bash
❯ echo "texto dentro do arquivo" > arquivoGit.txt
❯ openssl sha1 arquivoGit.txt
SHA1(arquivoGit.txt)= 79348403eb6e289d17adb359a20c59722322e6fe
❯ nano arquivoGit.txt -> arquivo alterado
❯ openssl sha1 arquivoGit.txt
SHA1(arquivoGit.txt)= 2560106dafcd2b80c70e561ba0e6d5e764e852f4
❯ nano arquivoGit.txt -> removida alteração
❯ openssl sha1 arquivoGit.txt
SHA1(arquivoGit.txt)= 79348403eb6e289d17adb359a20c59722322e6fe
```

### Objetos fundamentais
Qualquer mudança que ocorra em um repositório será notada, pois os blobs, threes e commits, cada um deles possuem seu próprio sha1, e havendo uma mudança em qualquer arquivo o sha1 do repositório mesmo irá ser alterado. Esse sistema permite um sistema distribuído e seguro dos arquivos, porque não permite que haja alterações não notadas no código.
- **Blobs**: mantêm os metadados de um arquivos do repositório, tem seu próprio sha1.
- **Trees**: armazenam os Blobs, guardando seu próprio sha1 (se o sha1 de um blob muda, consequentemente o da three também) e também apontando para outras threes.
- **Commits**: junta tudo, pois aponta para uma three, um parent (último commit feito antes), autor e mensagem. O commit também possuí seu próprio código sha1.

### Chaves SSH
Forma de autenticação de usuários no Github por criar uma conexão segura e encriptada entre duas máquinas (o próprio github e o seu pc). Funciona com chaves públicas e chaves privadas.

Tutorial
- Para criar a chave: `ssh-keygen -t ed25519 -C seuemail@gmail.com`
- Em home/.ssh: `cat id_rsa.pub`
- Copiar conteúdo (chave pública) e colar no github, em nova chave (Settings > SSH and GPG Keys > New SSH Key)

#### Token
Outra forma de autenticar para enviar mudanças, você coloca o e-mail e usa esse token como senha.

Tutorial
- Settings > Developer settings > Personal acess token > Generate new token
- Select scope > repo e data de expiração
- Copie o token quando gerado
- A partir de então, use o clone com link da função HTTPS e cole o token quando pedido

## Repositórios
### Repositório local
Repositório de desenvolvimento, ou local, é o seu pc em que você trabalha sozinho.

**Ciclo de vida**
- **untracked**: om o `git add` um arquivo untracked é movido para o estado de tracked, mais especificamente staged
- **tracked**
	- **unmodified**: aqui estão os arquivos commitados
	- **modified**: havendo qualquer modificação de um arquivo ele vai para esse estado (o git saberá disso pela alteração do SHA1 do respectivo arquivo); com o comando `git add` ele vai para o status de staged
	- **staged**: aqui estão os arquivos prontos para um `git commit`

### Repositório remoto
- No servidor, é o repo compartilhado pelas pessoas que trabalham naquele projeto
- O conteúdo do repo local vai para o remoto através dos commit feitos e com o comando `git push`
- Saber para onde aponta (remotamente) um repo local com o comando `git remote -v`

Fluxos possíveis para trabalhar com repositórios remotos:
Criar um novo repositório na linha de comando

```bash
echo "# bootstrap-site" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:giopin/bootstrap-site.git
git push -u origin main
```

Ou empurrar um repositório existente a partir da linha de comando

```bash
git remote add origin git@github.com:giopin/bootstrap-site.git
git branch -M main
git push -u origin main
```
	
## Comandos
- `git init` inicializa o versionamento de um repositório
	- Cria pasta oculta `.git` com a estrutura própria do git: `HEAD  config  description  hooks/  info/  objects/  refs/`
- `git add` adiciona arquivos que entrarão dentro do controle de versionamento do git
	- `git add *` incluirá todos os arquivos do dir
	- `git add arquivo.md` incluirá arquivo(s) específico(s)
- `git commit` 	envelopa todos os arquivos no status de prontos para serem classificados dentro de um pacote de mudanças, ou foto do momento (snapshot); quando commitados, os arquivos vão para o status de unmodified.
	- É como um registro de um diário, com o comando completo: `git commit -m "mensagem"`
- `git status` ajuda a saber em qual status de ciclo de vida estão os arquivos e repos.
	- Um comando simples para saber qual branch você se encontra, quais arquivos foram alterados e também quais arquivos já estão prontos para serem commitados.
- `git push` encaminha ao repositório remoto, o comando inteiro `git push origin main`
- `git pull` traz as mudanças do repositório remoto para o seu repositório local, o comando inteiro `git pull origin main`
- `git clone` clona um repo remoto no seu pc, o comando completo `git clone <link>`
- `git diff` para saber o que exatamente foi alterado em um arquivo.
- `git branch` branch é como se fosse uma realidade alternativa (ramificação) onde em algum ponto irá se juntar com a realidade principal; o comando permite criar, listar, renomear e excluir ramificações.
- `git merge` fusão de duas branches, quer dizer que houve uma fusão ou junção de códigos em uma única branch.
- `git tag` o comando é utilizado para criar as versões do seu projeto.

```bash
git tag v1.0.0

//para apagar a tag
git tag -d v1.0.0
```

O formato padrão para uma tag é `Vx.y.z`, sendo:
- `V` sigla para a palavra versão.
- `x` chamada de **Major** (versão principal do projeto)
- `y` chamada de **Minor** (adições de novas funcionalidades)
- `z` chamada de **Patchs**(correções de bugs no sistema)

[[Versionamento semântico]]

- [ ] `git rebase`
- [ ] `git reset`
- [ ] `git fetch`
	
## Conflitos
Acontecem quando existem duas alterações em uma mesma linha ou quando o código no github (remoto) tem algo a mais que você não possuí no seu projeto (local).

Para resolver conflitos você deve usar o comando `git pull` para baixar do servidor as alterações. Abrindo o arquivo, deve localizar onde está havendo conflito (o git irá juntar as edições de mesma linha no arquivo) e alterar a linha do conflito, escolhendo qual deve ser a versão final do arquivo. Após isso deve usar o comando `git push` para subir suas alterações.

## Git Flow
É uma ideia abstrata de como organizar suas branches para ter um controle maior sobre o que é feito dentro do seu projeto. Seguindo o projeto com esse fluxo, há maiores garantias de que ninguém no time irá atropelar ou perder código em merges falhos onde haverão conflitos.

```
Master─────────────────────Hotfix
└──────Releases────────────Bugfix
       └─────Develop───────Bugfix
             └─────Features
                   └───────Tasks
```

`Master` - branch responsável pelo ambiente que roda em Produção
- `Hotfix`(es) - responsável por corrigir algum erro critico que impeça o cliente de executar alguma função em ambiente de produção.

`Releases` - responsável por gerenciar e documentar todas as alterações feitas a cada deploy
`Develop` - branch onde sempre será criada e/ou mergeadas novas features
- `Bugfix`(es) - responsável por corrigir bugs pequenos em ambiente de desenvolvimento (develop) ou homologação (release).

`Features` - branchs responsáveis por desenvolver estórias do projeto
- `Tasks` - branch relacionada a uma feature (estória) descrevendo sempre um objetivo a ser trabalhado