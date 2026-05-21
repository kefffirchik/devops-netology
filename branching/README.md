# Ветвление, merge и rebase

В рамках задания были созданы ветки:

- main
- git-merge
- git-rebase

Ветка git-merge была объединена с main через merge.

Ветка git-rebase была перебазирована на main с разрешением конфликтов, после чего объединена с main.

Итоговая история проверена командой:

git log --oneline --graph --all

## Commit Graph

*   0addf11 (HEAD -> main, origin/main, origin/HEAD) Merge branch 'git-merge'
|\  
| * 97ee55e (origin/git-merge, git-merge) merge: use shift
| * 552d4ad merge: @ instead *
| * d289e36 (fix) prepare for merge and rebase
| * 0ecd636 (origin/fix) VS Code changes
| * 6cf451a Update README in fix branch
* | ba95c87 (origin/git-rebase, git-rebase) git-rebase 1
* | 546c57e (tag: v0.1, tag: v0.0, gitlab/main) Change README.md
* | 19f6037 Change README.md
* | 8622bbd README.md change
* | 36898f5 Moved and deleted
|/  
* 4fab8e6 Prepare to delete and move
* 2c9af7d Added gitignore
* f167460 First commit
* 839a307 Initial commit

- [История коммитов](https://github.com/kefffirchik/devops-netology/commits/main)
- [Network graph](https://github.com/kefffirchik/devops-netology/network)
