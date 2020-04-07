# GIT & GITHUB

Guia prático para iniciantes.

### Instalação

https://git-scm.com/download

# SCENES

- [x] 01. Criar pontos na história de produção do projeto.
- [x] 02. Verificar mudanças feitas no seu projeto.

- [x] 03. Começar uma nova funcionalidade no projeto, sem estragar o que já foi feito.
- [x] 04. Adicionar as novas funcionalidades ao projeto em produção.
- [x] 05. Deletar a 'branch' da novo funcionalidade, depois de aplicar no projeto.

- [x] 06. Colocar o projeto na nuvem.

- [x] 07. Pegar um projeto já iniciado, para trabalhar com o time
- [x] 08. Necessário resolver um conflito.
- [x] 09. Antes de enviar a resolução, precisamos atualizar o projeto local.

- [x] 10. Voltar um arquivo para um determinado momento da linha do tempo.
- [x] 11. Recuperar um arquivo deletado.

### Tabela de Comandos Git Utilizados

Comandos | Descrição
-------- | ---------
`git init    ` |  Inicia a linha do tempo
`git add     ` |  Adiciona ou atualiza mudanças para irem para a linha do tempoo
`git commit  ` |  Adiciona um ponto na linha do tempo
`git log     ` |  Visualiza os pontos na linha do tempo / commit
`git status  ` |  Informa o estado das alterações do nosso projeto
`git show    ` |  Apresenta determinado ponto na história
`git branch  ` |  Gerenciar novas linhas do tempo
`git checkout` |  Manipula as linhas do tempo
`git merge   ` |  Unir linhas do tempo
`git push    ` |  Envia alterações locais para o repositório remoto
`git clone   ` |  Clonar um projeto / repositório
`git pull    ` |  Puxa do repositório remoto


#### 01. Criar pontos na história da criação do projeto.

```
git init
```

```
touch landingpage.html
vim landingpage.html
. Adiciona: landing page finalizada
. :wq
```

```
git add landingpage.html

git commit -m "added landing page"

git log
```


#### 02. Verificar mudanças feitas no seu projeto.

```
vim landingpage.html
. Alterar: landing page alterada
. :wq
```

```
git status

git add landingpage.html

git commit -m "updated landing page"

git status

git log

git show f91b8f5

git show
```

#### 03. Começar uma nova funcionalidade no projeto, sem estragar o que já foi feito.

```
git branch feature/cart

git checkout feature/cart
```

```
touch cart.html
. vim cart.html
. Adicionar: carrinho em construção
. :wq
```

```
git status

git branch

git checkout master

git checkout feature/cart

git status

git add cart.html

git commit -m "added cart"

git log

git checkout master

ls -al     ( não tem cart.html )

git checkout feature/cart
```

```
. vim cart.html
. Alterar: carrinho finalizado
. :wq
```

```
git status

git add car*

git commit -m "cart ok"

git checkout master

ls -al     ( não tem cart.html )

git status

git branch
```

#### 04. Adicionar as novas funcionalidades ao projeto em produção.

```
git checkout master

ls -al     ( não tem cart.html )

git branch

git merge feature/cart

ls -al     ( tem cart.html )

git status

git log

git show
```

#### 05. Deletar a 'branch' da nova funcionalidade, depois de aplicar no projeto.

```
git branch -D feature/cart

git branch
```


#### 06. Colocar o projeto na nuvem.

- Criar uma conta em um servidor remoto 'git' (**GitHub**, GitLab, BitBucket,...)
- Crir um repositório para o projeto no servidor remoto ( nome repositório: git-basic )

Via | Link
--- | ----
HTTP | [https://github.com/carvalholc/git-basic.git]() 
SSH | [git@github.com:carvalholc/git-basic.git]()


```
git remote add origin https://github.com/carvalholc/git-basic.git

git remote -v

git push -u origin master     ( somente no primeiro push )
. user and password

. Olhar o repositório 'git-basic' no servidor remoto ( mostra os arquivos )

git remote

git remote rm <branch>

git status
```

```
. vim landingpage.html
. Alterar: landing page alterado (1)
. :wq
```

```
git status

git add .

git commit -m "added README; update landing"

git status

git log

git push
```
*Enter user and password*

> Olhar o repositório 'git-basic' no servidor remoto ( mostra os arquivos )
>
> **Nota:** Para não precisar adicionar 'user' e 'password'

```
git config credential.helper store

git push origin master
```

#### 07. Pegar um projeto já iniciado, para trabalhar com o time

> Pegar o link de um projeto no servidor remoto

```
git clone https://github.com/maykbrito/instagram-profile-header.git

ls -al

cd instagram-profile-header

git status
```

#### 08. Necessário resolver um conflito.

```
git checkout -b teste

ls -al
```

> vim package.json
>  Tirar a linha: "description"
> :wq

```
git status

git commit -am "update package.json"     ( or 'git add .' and 'git commit -m ""')

git checkout master
```

>  vim package.json
> Alterar a linha: "description": "alterado"
> :wq

```
git status

git add .

git commit -m "package.json update (new)"

git status

git branch

git merge teste
```

> Abri o arquivo "package.json" e corrigir o conflito
> save

```
git status

git commit -am "conflict resolved"

git status

git log

cd ..

ls -l

rm -Rf instagram-profile-header

ls -al
```

#### 09. Antes de enviar a resolução, precisamos atualizar o projeto local.

> 1. Simular que um outro desenvolvedor tenha alterado algo do projeto no servidor remoto
> 2. Alterar o arquivo README.md, retirando ou adicionando ou deletando linha(s)
> 3. Efetuar 'commit' no servidor remoto

###### Ir para o repositório local

```
git status      ( nenhuma alteração para subir )

git pull
```

> Ao final do dia subir todas as alerações

```
git push
```

#### 10. Voltar um arquivo para um determinado momento da linha do tempo.

> Voltar o arquivo package.json ( encontrar o momento para retornar )

```
git log

git checkout <id> -- package.json
```

> Retornou o "description" para ""

```
git status

git commit -am "restore package.json"

git status

git pull
```

#### 11. Recuperar um arquivo deletado.

##### 11.1. [ antes 'commit' ] Deletado um arquivo do repositório local.

```
ls -al

git status      ( avisa que o arquivo foi deletado )

git checkout -- <nome arquivo>      ( retorna o arquivo do ultimo log )

git status      ( avisa que tem arquivo para 'git add' e 'git commit' )
```

##### 11.2. [ depois 'commit' ] Deletado um arquivo do repositório local.

```
git status      ( avisa que o arquivo foi deletado )

git commit -am "delete <arquivo>"

git status

git checkout -- <nome arquivo>      ( retorna erro, o arquivo do ultimo log não existe )

git log

git checkout <id log> -- <nome arquivo>      ( retorna erro, o arquivo do ultimo log não existe )

ls -al

git status

git add .

git commit -m "restore <arquivo>"

git push  ( para enviar alteraçções para o repositório remoto )
```

### < End >


# Alias no Git

Arquivo: .gitconfig

[alias]
  ci = commit
  co = checkout
  cm = checkout master
  cb = checkout -b
  st = status -sb
  sf = show --name-only
  lg = log --pretty=format:'%Cred%h%Creset %C(bold)%cr%Creset %Cgreen<%an>%Creset %s' --max-count=30
  incoming = !(git fetch --quiet && git log --pretty=format:'%C(yellow)%h %C(white)- %C(red)%an %C(white)- %C(cyan)%d%Creset %s %C(white)- %ar%Creset' ..@{u})
  outgoing = !(git fetch --quiet && git log --pretty=format:'%C(yellow)%h %C(white)- %C(red)%an %C(white)- %C(cyan)%d%Creset %s %C(white)- %ar%Creset' @{u}..)
  unstage = reset HEAD --
  undo = checkout --
  rollback = reset --soft HEAD~1

.: Menos usados
  rollforward = commit -c ORIG_HEAD
  conflicts = !git ls-files -u | cut -f 2 | sort -u


[alias]
    pom = push origin master -u
    ps = push
    ci = commit
    co = checkout
    cm = checkout master
    cb = checkout -b
    st = status -sb
    sf = show --name-only
    lg = log --pretty=format:'%Cred%h%Creset %C(bold)%cr%Creset %Cgreen<%an>%Creset %s' --max-count=30
    incoming = !(git fetch --quiet && git log --pretty=format:'%C(yellow)%h %C(white)- %C(red)%an %C(white)- %C(cyan)%d%Creset %s %C(white)- %ar%Creset' ..@{u})
    outgoing = !(git fetch --quiet && git log --pretty=format:'%C(yellow)%h %C(white)- %C(red)%an %C(white)- %C(cyan)%d%Creset %s %C(white)- %ar%Creset' @{u}..)
    unstage = reset HEAD --
    undo = checkout --
    rollback = reset --soft HEAD~1


. Com isso basta digitar git ci qualquer mensagem (isso mesmo! sem double quotes...) para agilizar e facilitar a nossa vida.
ci = "!f() { git commit -m \"$*\"; }; f"

. Deixo como sugestão também, um que uso e gosto muito, que basicamente serve para apagar todas as branches locais exceto algumas:
brclear = !git branch | grep -v 'master\\|development\\|staging' | xargs git branch -D

. git kraken

. Muito legal, uso o alias do Oh My Zsh mas adicionei alguns desses no ZSH_CUSTOM. Ficou show!

. Git Flow // Dicionário do Programador
https://www.youtube.com/watch?v=oweffeS8TRc

. Padronizando mensagens de commit do Git | Code/Drops #12
https://www.youtube.com/watch?v=erInHkjxkL8

. Debug de aplicações Node.js com VSCode | Code/Drops #11
https://www.youtube.com/watch?v=bVAhNaxBEjM

. Github CLI está no ar | Code/Drops #19    ( CLI -> Command-line Interface )
https://www.youtube.com/watch?v=u3V7mSPkYyk

. CodeQuinta #5 - Fluxo Git & Github
https://www.youtube.com/watch?v=2T2l2rGRzXs

. SOLID (O básico para você programar melhor) // Dicionário do Programador
https://www.youtube.com/watch?v=mkx0CdWiPRA


. Testes Automátizados ( Técnica TDD )
. Git Flow
. Integração Continua
. Build Continuo
. Deploy Continuo
