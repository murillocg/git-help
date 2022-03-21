# Git Help - Tips for using

#### I want to commit to the PR of a colleague who went on vacation
```
git remote add mycolleague https://github.com/mycolleague/project.git
git push mycolleague pr-449:{his branch name - remote branch}
```

#### I want to force a commit without change to trigger the pipeline build
```sh
git commit --allow-empty -m "Trigger Build"
```

#### I have a changed local file that shouldn't be committed for now

```sh
git update-index --assume-unchanged config/database.yml
```
* To undo this setting:
```sh
git update-index --no-assume-unchanged config/database.yml
```

#### I pulled the code, there was a conflict in the merge and I want to undo the pull (to delete the local branch)

```sh
git merge --abort
```

#### Remove local branch

```sh
git branch -D 'branch_name'
```

#### Remove remote branch

```sh
git push origin --delete 'branch_name'
```

#### Add remote repository

```sh
git remote add upstream <remote_reporitory_url>
```

#### Create local branch from remote

```sh
git fetch upstream <remote_branch>:<local_branch>
```

#### Download pull request for local testing

```sh
git fetch upstream pull/<id>/head:<local_branch>
git checkout <local_branch>
```

#### Update local branch with code from pull request

```sh
git pull upstream pull/<id>/head
```

#### Undo last unsent commit (done on wrong branch, for example)

```sh
git reset HEAD~1
```

#### Remove files later added to .gitignore

```sh
git rm -r --cached . 
git add .
git commit -am "Remove ignored files"
```

### Integrar código de um commit/branch em outra branch
* descobrir o hash do commit com git log
* ir para branch onde deseja integrar o código

```sh
git cherry-pick <hash_commit>
git add .
git commit
```

### Export project to zip (taking into account ignored files such as builds, logs, etc)

```sh
git archive --format zip --output <file_name>.zip master
```
