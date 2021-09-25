# Git - A guide on how to use git via the command line

Before I talk about git, I wanted to define a few key terms that I will be using in this guide. Any new vocabulary in the guide will be highlighted like `so`.

* `Version Control System` : A version control system, also known as a VCS, keeps tracks changes made to files. A VCS logs information about what changed, who changed it, and why it was changed.

* `Terminal` : A terminal is an interface in which you can type and execute text based commands. The terminal is very powerful and gives you direct control over a computing environment. 

* `Commands` : A command is a instruction to a computer program in order to perform a certain task. In other words, commands run programs. Keep in mind that a lot of commands run via a terminal cannot be undone. It is key to understand what you are exactly doing with a command before you execute it. 

## 1. What is Git? 

Well, now that we have covered our bases, let's talk about Git. It's important to note that `Git` and `Github` are two completely different systems. Git is a version control system. Github is a website for hosting (storing) projects that use git. I like to think of it in this way: Git is a tool and Github is like Google Drive. You can use git to "push" your projects to Github. 

So why use git? Well, git is useful for coordinating work among several people working on the same codebase. Changes are logged in checkpoints known as `commits`. And git is not just for programming. You can use it to track changes to an essay, or save multiple revisions of art. 

Before you move on to the rest of this guide, make sure you have git installed. Linux and MacOS systems have git installed by default, so you don't have to install anything. If you are windows, check out this [guide](https://www.computerhope.com/issues/ch001927.htm#:~:text=By%20default%2C%20Git%20is%20installed,not%20include%20a%20Git%20command). 

## 2. Git Commands and how to use them.

You have a project and you want to use git. How? Let's go through the steps. To make this more effective, assume that you have a project folder named __MyFolder__. These are the contents of __MyFolder__ before we set up git and perform actions on it.

__MyFolder\/__

* __essay.text__


### Git Init

The first thing you have to do is initialize a `repository`. A repository is basically your project folder with a special git folder installed in it (.git folder). You can take a project folder that you have and turn it into a repository using the following command.

`git init`

This allows you to use the other commands shown below and is the first step you need to do in order to use git. You only need to do this in a specific project ONCE.

After running `git init` on __MyFolder__, these are the contents of __MyFolder__.

__MyFolder\/__

* __essay.text__
* __.git__ (this is a hidden file, you won't be able to see it through a file explorer application but if you can run git commands it is there!)

And thats all you have to do to "install" git onto your project. 

### Git Clone

What if you want to use an existing repository, like a codebase on github? This is where `git clone` comes into play. You can "clone" a repository onto your computer, allowing you to make edits on it with git.

`git clone <repo url>`

This is just like `git init`, but instead of taking a folder and turning it into a repository, you are downloading your repository from the internet.

After running `git clone https://github.com/msoham123/MyFolder.git` on a computer with no __MyFolder__, these are the contents of the newly created__MyFolder__.

__MyFolder\/__

* __essay.text__
* __.git__ (this is a hidden file, you won't be able to see it through a file explorer application but if you can run git commands it is there!)


