
# ToDo

- [ ] Alias no Git
- [ ] GitFlow
- [ ] Padronizando mensagens de commit do Git
- [ ] Debug de aplicações Node.js com VSCode
- [ ] Github CLI está no ar
- [ ] GitHub Actions
- [ ] Fluxo Git & Github
- [ ] SOLID (O básico para você programar melhor)

---

- [ ] Testes Automátizados ( Técnica TDD )
- [ ] Git Flow
- [ ] Integração Continua
- [ ] Build Continuo
- [ ] Deploy Continuo

---


## Alias no Git

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

[<< Voltar](README.md)
