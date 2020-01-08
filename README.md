# Git Work Flow

[TOC]

[Credits to Codemy School ](https://www.youtube.com/watch?v=uUuTYDg9XoI&list=PLjQo0sojbbxVHcVN4h9DMu6U6spKk21uP)


## 3 Branches

- Master 

- Develop (Staging)

- Feature/ (Contains all the new features)

  

> ## Process (without Git Flow)
> 
>
> ### Branch Develop 
>
>
> ```json 
> git checkout -b feature/<new-feature>
> ```
>
> **Work on your feature and when the feature is ready for staging**
>
> ```json
> git checkout develop
> ```
>
> **Good practice would be to run tests before merging!**
>
>  ```json
> git merge feature/<new-feature>
>  ```
>
> **Delete the feature branch**
>
> ```json
> git branch feature/<new-feature> -D
> ```
>



# Setup SSH

*This will allow you to push to github*

**Open up your terminal**
*Follow the steps*
```json
ssh-keygen -t rsa -C <your email>
```

**Get your public key**
```json
cat <file-name>.pub
```

Go to [settings/keys](https://github.com/settings/keys) and save the ssh key.

<!-- Make sure you're in the master branch -->

**Create a new repo in github**

```json
git remote add origin https://github.com/<yourgithub>/<project-name>.git
git push origin master
git push origin develop
```

[Set the default branch to develop](https://github.com/<your-username>/git-workflow/settings/branches)



# Get Started



## Git Flow

Git Flow gives you a set of commands to work with. By default it's already installed.

Run `git flow help` to check whether it's on your machine.

**Incase it's not installed**
[How to install](https://www.npmjs.com/package/gitflow)

```json
git flow init
```

#### Create a new feature

*When creating a new feature make sure to be in the Develop branch*

```json
git flow feature start <feature-name>
```

#### When feature is ready for staging

```json
git add -A
git commit -am "<Your comment>"
```



#### Check current features

*This will give us a list of all on-going features*

```json
git flow feature
```

#### Pushing a feature remotely

```json
git flow publish feature <feature-name>
```

# Pull Requests


#### Make a pull request

Go to Github select your recently added branch and click on the button **Create pull request**. At this point people can review your code, which helps with making sure that you push solid code.

![img](https://i.imgur.com/DhTnaSj.png)


#### Merge feature with develop branch
*This will close the pull request, and remove the feature branch both locally and remote.*

```json
git flow feature finish <feature-name>
```

####  Push to remote development branch

```json
git push origin develop
```


# Release Branch
*This is the final step*

```json
git flow release start 1.0.1
```

**modify your package.json version**

```json 
git commit -am "updated version"
git flow finish
```

*Follow steps, give the tag the version number*

```json
git checkout master
git push origin --all --follow-tags
```



# Snippets

*Copy paste in your terminal*

```json
alias: git graph
git config --global alias.graph "log --graph --oneline --decorate "

alias: git graph1
git config --global alias.graph "log --graph --oneline --decorate --all"
```


