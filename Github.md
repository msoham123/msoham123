# Git - A guide on how to use git via the command line

Before I talk about git, I wanted to define a few key terms that I will be using in this guide. Any new vocabulary in the guide will be highlighted like `so`.

* `Version Control System` : A version control system, also known as a VCS, keeps tracks changes made to file. A VCS logs information about what changed, who changed it, and why it was changed.

* `Terminal` : A terminal is an interface in which you can type and execute text based commands. The terminal is very powerful and gives you direct control over a computing environment.

* `Commands` : A command is an instruction to a computer program in order to perform a certain task. In other words, commands run programs. Keep in mind that a lot of commands run via a terminal cannot be undone. It is key to understand what you are exactly doing with a command before you execute it.

## 1. What is Git?

Well, now that we have covered our bases, let's talk about Git. It's important to note that `Git` and `Github` are two completely different systems. Git is a version control system. GitHub is a website for hosting (storing) projects that use git. I like to think of it in this way: Git is a tool and GitHub is like Google Drive. You can use git to "push" your projects to GitHub.

So why use git? Well, git is useful for coordinating work among several people working on the same codebase. Changes are logged in checkpoints known as `commits`. And git is not just for programming. You can use it to track changes to an essay, or save multiple revisions of art.

Before you move on to the rest of this guide, make sure you have git installed. Linux and macOS systems have git installed by default, so you don't have to install anything. If you are windows, check out this [guide](https://www.computerhope.com/issues/ch001927.htm#:~:text=By%20default%2C%20Git%20is%20installed,not%20include%20a%20Git%20command).

## 2. Git Commands and how to use them.

You have a project, and you want to use git. How? Let's go through the steps. To make this more effective, assume that you have a project folder named __MyFolder__. These are the contents of __MyFolder__ before we set up git and perform actions on it.

``` 
MyFolder/

* essay.text
* .git (this is a hidden file, you won't be able to see it through a file explorer app)
```


### Git Init

The first thing you have to do is initialize your `repository`. A repository consists of a special git folder installed in it (.git folder). You can take a project folder that you have and add a git repository using the following command.

`git init`

This allows you to use the other commands shown below and is the first step you need to do in order to use git. You only need to do this in a specific project ONCE.

After running `git init` on __MyFolder__, these are the contents of __MyFolder__:

``` 
MyFolder/

* essay.text
* .git (this is a hidden file, you won't be able to see it through a file explorer app)
```

And that's all you have to do to "install" git onto your project.

### Git Clone

What if you want to use an existing repository, like a codebase on GitHub? This is where `git clone` comes into play. You can "clone" a repository onto your computer, allowing you to make edits on it with git.

`git clone <repo url>`

This is just like `git init`, but instead of taking a folder and adding a repository, you are downloading your folder and repository from the internet.

After running `git clone https://github.com/msoham123/MyFolder.git` on a computer with no __MyFolder__, these are the contents of the newly created __MyFolder__:

``` 
MyFolder/

* essay.text
* .git (this is a hidden file, you won't be able to see it through a file explorer app)
```

### Git Status

Great, so we now have our repository all set up and ready to use! What do we do next? Well, remember that the purpose of git is track changes made to file. There needs to be a way where we can visualize these changes easily. This is where `git status` comes into play.

`git status`

The `git status` command is very straightforward. It displays which files have been modified. So, if you made a bunch of changes to multiple files and don't remember which ones you had changed, `git status` is a command that will show you.

After running `git status` on repository __MyFolder__ in which we modified __essay.text__, this is what is displayed:

```
On branch main
Your branch is up to date with 'origin/main'. 

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        essay.text     

nothing added to commit but untracked files present (use "git add" to track)
```


Note how the command shows you untracked (changed) files. In this case, we made changes to __essay.text__, so that is what is shown as untracked.

### Git Add

Notice that `git status` told us to use `git add` to track the file, or to "add it". Well, what are we adding it to? Here is a useful diagram to visualize this.

<!-- ![](https://www.edureka.co/blog/wp-content/uploads/2016/11/Git-Architechture-Git-Tutorial-Edureka-2.png)
 -->

![](https://git-scm.com/figures/18333fig0106-tn.png)

The changes that we have made reside in our working directory. When you use `git add`, we add our changes to the staging area. Think of the staging area like a rough draft space. We're letting git know that these are our rough drafts. When we are ready to finalize them, we can use `git commit` to permanently modify the repository.

`git add <file path>`

This might seem a little odd at first. Why do we have to manually stage every change we make? Well, git gives us precise power over what we do. If we made edits to multiple files but only wanted to stage one, we could, and then we would only `git commit` that one change to the file. Git gives the user a lot of control.

Here's an example to really drive it in. After running `git status` on repository __MyFolder__ in which we modified __essay.text__, we add our changes and stage them using `git add`:


 ```
msoham123> git status
 
On branch main
Your branch is up to date with 'origin/main'. 

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        essay.text     

nothing added to commit but untracked files present (use "git add" to track)

msoham123> git add essay.text
```

And that's it! Now, the changes we made to essay.text are ready to be committed!


### Git Commit

It isn't quite clear at first what "commit" means. Status was pretty self-explanatory and so was "add". But the way I like to think about `git commit` is that the "commit" signifies that you are committing your change to the repository. In other words, you are telling git that this your final draft.


![](https://git-scm.com/figures/18333fig0106-tn.png)

Let's go back to this diagram. We've already established that we have a working directory, the place in which we actually make the changes. Adding files to the staging area is like marking your changes as rough drafts. So committing files is the final step: actually changing your repository and submitting your changes as the final draft.

This might once again seem odd. When I make changes, am I not changing the file itself? Well, you are, but only in the working directory. You need to stage files and commit them in order to actually change the files in the repository.

`git commit -m "<name of commit>"`

What `git commit` does is that it takes all of your files (rough drafts) in the staging area, and replaces the old corresponding files in the repository with the new one. This replacement is saved in history as a `commit`, and therefore needs to be assigned a name in order to provide context as to what was changed.

Let's finalize the changes we made to __essay.text__. After running `git status` on repository __MyFolder__ in which we modified __essay.text__, we add our changes and stage them using `git add`. Once the files are staged, we can commit them using `git commit`. I added a conclusion paragraph to __essay.text__ so my commit will be as follows:


 ```
msoham123> git status
 
On branch main
Your branch is up to date with 'origin/main'. 

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        essay.text     

nothing added to commit but untracked files present (use "git add" to track)

msoham123> git add essay.text

msoham123> git commit -m"Added conclusion"

[main 3af59ea] Added conclusion
 1 file changed, 73 insertions(+), 19 deletions(-)
```

Notice how committing reminds you what changes have been made to repo. Our changes to __MyFolder__, specifically __essay.text__, are now properly updated in the git repository. Now that we have this down, this is where the fun begins :)

### Git Push

So we understand that we have a working directory, staging area, and repository. But what about GitHub? Isn't that also our repository but stored on the cloud? 

The cloud-based repository stored on sites like GitHub is called the remote repository, or `remote` for short. The diagram we had earlier was a little simple, so here's a more accurate one.

![](https://i.redd.it/nm1w0gnf2zh11.png)

Working tree is the same as working directory. 
