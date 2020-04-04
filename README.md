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
- [x] 11. Recuperar algo deletado.

* `git init` // inicia a linha do tempo
* `git add` // adiciona ou atualiza mudanças para irem para a linha do tempoo
* `git commit` // adiciona um ponto na linha do tempo
* `git log` // visualiza os pontos na linha do tempo / commit
* `git status` // informa o estado das alterações do nosso projeto
* `git show` // apresenta determinado ponto na história
* `git branch` // gerenciar novas linhas do tempo
* `git checkout` // manipula as linhas do tempo
* `git merge` // unir linhas do tempo
* `git push` // envia alterações locais para o repositório remoto
* `git clone` // clonar um projeto / repositório
* `git pull` // puxa do repositório remoto


#### 01. Criar pontos na história de produção do projeto.

git init

touch landingpage.html
vim landingpage.html
. Adiciona: landing page finalizada
. :wq

git add landingpage.html

git commit -m "added landing page"

git log


#### 02. Verificar mudanças feitas no seu projeto.

vim landingpage.html
. Alterar: landing page alterada
. :wq

git status

git add landingpage.html

git commit -m "updated landing page"

git status

git log

git show f91b8f5

git show


#### 03. Começar uma nova funcionalidade no projeto, sem estragar o que já foi feito.

git branch feature/cart

git checkout feature/cart

touch cart.html
. vim cart.html
. Adicionar: carrinho em construção
. :wq

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

. vim cart.html
. Alterar: carrinho finalizado
. :wq

git status

git add car*

git commit -m "cart ok"

git checkout master

ls -al     ( não tem cart.html )

git status

git branch


#### 04. Adicionar as novas funcionalidades ao projeto em produção.

git checkout master

ls -al     ( não tem cart.html )

git branch

git merge feature/cart

ls -al     ( tem cart.html )

git status

git log

git show


#### 05. Deletar a 'branch' da nova funcionalidade, depois de aplicar no projeto.

git branch -D feature/cart

git branch


#### 06. Colocar o projeto na nuvem.

. Criar uma conta em um servidor remoto 'git' (GitHub*, GitLab, BitBucket,...)
. Crir um repositório para o projeto no servidor remoto ( nome repositório: git-basic )

HTTP: git remote add origin https://github.com/carvalholc/git-basic.git
SSH : git remote add origin git@github.com:carvalholc/git-basic.git

git remote -v

git push -u origin master     ( somente no primeiro push )
. user and password

. Olhar o repositório 'git-basic' no servidor remoto ( mostra os arquivos )

git remote

git remote rm <branch>

git status

. vim landingpage.html
. Alterar: landing page alterado (1)
. :wq

git status

git add .

git commit -m "added README; update landing"

git status

git log

git push
. user and password

. Olhar o repositório 'git-basic' no servidor remoto ( mostra os arquivos )

[ Nota: ] Para não precisar adicionar 'user' e 'password'
git config credential.helper store
. not necessary user and password

git push


#### 07. Pegar um projeto já iniciado, para trabalhar com o time

. Pegar o link de um projeto no servidor remoto

git clone https://github.com/maykbrito/instagram-profile-header.git

ls -al

cd instagram-profile-header

git status


#### 08. Necessário resolver um conflito.

git checkout -b teste

ls -al

. vim package.json
. Tirar a linha: "description"
. :wq

git status

git commit -am "update package.json"     ( or 'git add .' and 'git commit -m ""')

git checkout master

. vim package.json
. Alterar a linha: "description": "alterado"
. :wq

git status

git add .

git commit -m "package.json update (new)"

git status

git branch

git merge teste

. Abri o arquivo "package.json" e corrigir o conflito
. save

git status

git commit -am "conflict resolved"

git status

git log

cd ..

ls -l

rm -Rf instagram-profile-header

ls -al


#### 09. Antes de enviar a resolução, precisamos atualizar o projeto local.

. Simular que um outro desenvolvedor tenha alterado algo do projeto no servidor remoto
. Alterar o arquivo README.md, retirando ou adicionando ou deletando linha(s)
. Efetuar 'commit' no servidor remoto

. Ir para o repositório local

git status      ( nenhuma alteração para subir )

git pull






#### 10. Voltar um arquivo para um determinado momento da linha do tempo.



#### 11. Recuperar algo deletado.










git pull

. ver as alterações


. Voltar o arquivo package.json 
git log

git checkout <id> -- package.json
. retornou o "description" para ""

git status

git commit -am "restore package.json"

git status

git pull

git push  ( para enviar alteraçções para o repositório remoto )







