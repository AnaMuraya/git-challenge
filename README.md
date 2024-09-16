# Git Challenge

There are two branches, `add-echo` and `add-reverse`. The goal of this challenge is to use `git rebase` to bring both commits onto master. When finished there should be no merge commits or branching. For example, `git log` on the `master` branch should look similar to this:

```bash
/challenge-git master
⚡ git log
61a2c67 feat: add reverse route (David Guttman, 7 minutes ago)
2c2c5d6 feat: add echo route (David Guttman, 10 minutes ago)
dcc4c0b docs: add more instructions (David Guttman, 11 minutes ago)
...
```

## Instructions

How to attempt this challenge:

1) Create a new repo in your account and note the git url
2) Clone this repo
3) Solve the challenge
4) Set your new repo as the origin: `git remote set-url origin ${your repo url}`
5) Push your solution to your repo
You must follow these steps for your solution to be accepted -- forks or other methods will not be considered.

## Solution

```bash
git clone git@github.com-personal:Interlincx/challenge-git.git #clone the repo
cd challenge-git/
code .
git checkout add-reverse
git rebase master #adds new changes from main into add-reverse, then on top, adds add-reverse changes
git checkout add-echo
git rebase master #adds new changes from main into add-echo, then on top, adds add-echo changes
git checkout master
git rebase add-reverse #adds new changes from add-reverse into main
git rebase add-echo #adds new changes from add-echo into main, then on top, adds main changes(previous add-reverse rebased changes in this case). Here you manually solve the conflicts that might appear.
git add . #Stage the resolved conflicts
git rebase --continue #Continue with the rebase
git log --oneline #To check the logs are how you'd like them to be.
git remote set-url origin <personal-repo> #Change the git remote to personal repo
git push #Push to your repo
```
