# Dicas para uso do git


#### Fiz pull, deu conflito no merge e quero desfazer o pull (para excluir a branch local);

```sh
git merge --abort
```

#### Remover branch local

```sh
git branch -D 'branch_name'
```

#### Remover branch remota

```sh
git push origin --delete 'branch_name'
```

#### Adicionar repositório remoto

```sh
git remote add upstream <url_do_repositorio_remoto>
```

#### Criar branch local a partir da remota

```sh
git fetch upstream <branch_remota>:<branch_local>
```

#### Baixar pull request para teste local

```sh
git fetch upstream pull/<id>/head:<branch_local>
git checkout <branch_local>
```

#### Atualizar branch local com código do pull request

```sh
git pull upstream pull/<id>/head
```

#### Desfazer último commit não enviado (feito na branch errada, por exemplo)

```sh
git reset HEAD~1
```

#### Remover arquivos adicionados posteriormente ao .gitignore

```sh
git rm -r --cached . 
git add .
git commit -am "Remove ignored files"
```

### Exportar projeto para zip (considerando arquivos ignorados, builds, logs, etc)

```sh
git archive --format zip --output <nome_arquivo>.zip master
```
