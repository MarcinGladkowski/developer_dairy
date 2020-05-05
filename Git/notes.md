Remotes and Upstream branches https://wanago.io/2020/04/06/geeky-with-git-remotes-upstream-branches/?fbclid=IwAR2lw9KrwJtoQO46yLeWp4Z-dgpZiJy0tiXNKJAG4OjpSmTbgxQky97o9M8

# GIT SOME COMMANDS


Sort branches by commiit date
`git branch --sort=committerdate`  

Checkout previous branch
`git checkout -`

List branches along with commit ID, commit message and remote
`git branch -vv`

Checkout file to specific branch
`git checkout feature/name -- <file>`

Shorter status
`git status -sb`

Line endings
> Windows \r\n (CRLF)
> UNIX \n (LF)
> MAC \r (CR)

`git config core.eol lf`
`git config core.autocrlf input`


---
Sources
* [How To Make Life Easier When Using Git](https://www.smashingmagazine.com/make-life-easier-when-using-git/)
* [Little Things I Like to Do with Git](https://csswizardry.com/2017/05/little-things-i-like-to-do-with-git/)