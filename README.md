## Setup

### Iniciar um novo repositório
```
$ git init
```

### Clonar um repositório
```
$ git clone url-do-repositorio.git .
```

### Deletar um repositório
```
$ rm -rf .git
```

### Adicionar um repositório remoto
```
$ git remote add origin url-do-repositorio.git
```

***

## Criando commits

### Checar status do repositório
```
$ git status
```

### Adicionar arquivos criados ou modificados na staging area
```
$ git add nome-do-arquivo
$ git add .
```
Seleciona apenas alguma(s) parte(s) modificadas para serem adicionadas na staged area separadamente para serem comitadas separadamente.
```
$ git add -p
```

### Criando um commit
```
$ git commit -m "mensagem"
```
Adiciona os arquivos modificados na staging area e cria o commit (não adiciona arquivos ainda não trackeados).
```
$ git commit -am "mensagem"
```

### Visualizar histórico de commits
```
$ git log
$ git log --graph
```
Visualiza um log mais completo com todas as ações realizadas. Permite recuperar coisas depois de um reset --hard.
```
$ git reflog
```

***

## Revertendo e resetando commits

### Revertendo modificações de um arquivo para a versão do último commit
```
$ git checkout nome-do-arquivo
```

### Revert
Desfaz as modificações do commit selecionado e cria um novo commit para essa ação.
```
$ git revert commit-id
```

### Resets
Todos os "resets" deletam os commits selecionados e alteram o histórico. O commit id passado no comando deve ser referente ao commit anterior ao(s) que deve(m) ser deletado(s) (utilizar com cautela pois altera o histórico, evitar utilizar caso já tenha enviado o(s) commit(s) ao repositório remoto para evitar conflitos com outros usuários).

#### Reset "soft"
Deleta o(s) commit(s) selecionado(s) e coloca os arquivos de volta na staging area (com os arquivos modificados).
```
$ git reset --soft commit-id
```

#### Reset "mixed"
Deleta o(s) commit(s) selecionado(s) e coloca os arquivos de volta na unstaged area (com os arquivos modificados).
```
$ git reset --mixed commit-id
```

#### Reset "hard"
Deleta o(s) commit(s) selecionado(s) e retorna os arquivos na versão do último commit atual (sem as modificações posteriores).
```
$ git reset --hard commit-id
```

***

## Corrigindo e alterando commits

### Amend
Edita o último commit. Pode-se adicionar novas modificações ou arquivos e/ou alterar a mensagem de commit. Antes de utilizar o comando, adicionar as novas modificações na staging area.
```
$ git commit --amend
```

### Rebase interativo
Seleciona os "x" últimos commits para serem agrupados em um único commit (utilizar pick + squash > obs: altera o histórico).
```
$ git rebase -i HEAD~x
```

### Fixup
Faz uma correção do commit selecionado, criando um novo commit com o prefixo “fixup!” adicionando as novas modificações. Interessante para se usar combinado com o comando “git rebase -i --autosquash” posteriormente para fazer um rebase dos commits com fixup.
```
$ git commit --fixup commit-id
```

***

## Branches

### Criar uma branch
```
$ git checkout -b nome-da-branch
```

### Listar branches
```
$ git branch
```

### Trocar de uma branch para outra
```
$ git checkout nome-da-branch
```

### Dar merge em uma branch
Alterar para a branch principal antes.
```
$ git merge nome-da-branch
```

### Deletar branches
```
$ git branch -D nome-da-branch
```

***

## Atualizando repositórios locais e remotos

### Push
Atualiza repositório remoto.
```
$ git push -u origin nome-da-branch
```

### Pull
Atualiza repositório local.
```
$ git pull -u origin nome-da-branch
```

Utilizar o comando "-u" para trackear a branch (não é necessário mais digitar "origin nome-da-branch" posteriormente).

***

## Utilidades

### Stash
Salva o estado das modificações sem fazer um commit (salva com stash, e ativa com apply). Útil para quando se está fazendo modificações dentro de uma branch errada, por exemplo (dar stash, alterar a branch, e dar apply).
```
$ git stash
$ git stash apply
```

***

## Referências

[workflows (artigo do bitbucket)](https://www.atlassian.com/git/tutorials/comparing-workflows)

[git-flow cheatsheet](http://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html)
