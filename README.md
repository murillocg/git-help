# Dicas para uso do git


* Fiz pull e deu conflito e quero desfazer o pull;
````
git merge --abort
````
* Remover branch local
````
git branch -D 'branch_name'
````
* Criar branch local a partir da remota
````
git fetch upstream <branch_remota>:<branch_local>
````
