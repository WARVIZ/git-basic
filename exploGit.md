
# Exemplos Comandos Git

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

[<< Voltar](README.md)
