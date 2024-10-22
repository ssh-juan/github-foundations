## Git Hidden Folder

There is a hidden folder called `.git` which tells you that our project is a git repo.

If we wanted to create a git repo in a new project we' create the folder and the initiliaze that repo using `git init`

```
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
git status
git add Readme.md
# makes changes to readme.md
git commit -a -m "add readme file"
```

## Cloning

We can clone three ways: HTTPS, SSH, Github CLI

Since we are using Github Codespaces we'll create a temporary directory in our workspace.

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

We will need to create our own SSH RSA key pair.

>Particulary in my case, using WSL did not work well. So I got a suggestion from a friend and began to use Git Bash, instead of WSL. And then it worked.

I had to create all the folders structure of SSH and also the SSH key and do the steps related to it.

We can test our connection here:
```
ssh -T git@github.com
```

### GitHub CLI

I installed the CLI via web browser and later started to use Git Bash to manipulate it.
> I used the following path link: https://github.com/cli/cli/releases/download/v2.52.0/gh_2.52.0_windows_amd64.zip

Then unziped it and moved the '.exe' file to /bin folder.

Later i moved to that folder and tried to check if it's working checking it's version.
```
cd /bin
./gh --version
```

```
gh auth login
gh clone
```

- Como clonar um repo via GitHub cli
```
gh repo clone {user/repo}
```

### HTTPS
```sh
git clone https://github.com/JuanBSoares/repo-generic.git
cd repo-generic
```

## Commits

When we want to commit code we can wright git commit which will open up the commit edit message in the editor of choice.
```sh
git commit
```
Set the global editor
```
git config --global core-editor emacs
```

Make a commit and commit message without opening an editor
```sh
git commit -m "comments"
```

## Branches

<<<<<<< HEAD
List of branches
```
git branch
```

Create a new branch
```
git branch {name}
```

Checkout the branch (switch to that branch)
```
git checkout {dev}
```

## Remotes

We can add remotes but often you will just add remote via upstream when adding a branch.

```ssh
got remote add ...
git branch -u origin new-feature
```

## Stashing

```
git stash list
git stash
git stash save my-name
git stash apply
git stash pop
```

* NOT USE IN A CLOUD ENV, BECAUSE YOU CAN LOST DATA

## Merging

```
git checkout dev
git merge main
```

## Add

When we want to stage changes that will be included in the commit.
We can use the . to add all the possbile files

```
git add Readme.md
git add .
```

## Reset

Reset allows you to move Staged changes to be Unstaged.
This is useful when you want to revert all files to be not commited.

```
git add .
git reset
```
> git reset will revert a git add .

## Status

Git status shows you what files will or will not be commited.

```
git status
```

## Gitconfig File

The Gitconfig file is what stores your global configurations for git such as email, name, editor and more.

Showing the contents of our .gitconfig file
```
git config --list
```

When you first install Git on a machine you are suppose to set up your name and email

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Log

Git log will show recent git commits to the git tree

## Push

When we want to push a repo to our remote origin.

```
git push
```