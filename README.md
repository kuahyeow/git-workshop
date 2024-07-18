# What is Git ?

Git is a _distributed_ **version control** system  
<a href="http://git-scm.com/about">http://git-scm.com/about</a>

## Setup

First thing to do is to setup your identity. This identifies you to
other people who download the project.

    $ git config --global user.name "Your Name"
    $ git config --global user.email your.email@example.com

## Starting your journey

First, fork (create your own copy of) and clone this repository:  
You can find the fork button at the top right of
the screen on a github repository, or more help about doing that [here](https://help.github.com/articles/fork-a-repo/).

    $ git clone git@github.com:charmcity-code/git-workshop.git

Once you have cloned your repository, you should now see a directory
called `git-workshop`. This is your `working directory`

    $ cd git-workshop
    $ ls

## The staging area

Now, let’s try adding some files into the project. Create a couple of
files.

Let’s create two files named `lincoln.txt` and `logan.txt`.

    $ touch lincoln.txt logan.txt

Let’s use a mail analogy.

In Git, you first add content to the `staging area` by using `git add`.
This is like putting the stuff you want to send into a cardboard box.
You finalize the process and record it into the git index by using
`git commit`. This is like sealing the box - it’s now ready to send.

Let’s add the files to the staging area

    $ git add .

## Committing

You are now ready to commit. The `-m` flag allows you to enter a message
to go with the commit at the same time.

    $ git commit -m "create two new files"

## Let’s see what just happened

We should now have a new commit. To see all the commits so far, use
`git log`

    $ git log

The log should show all commits listed from most recent first to least
recent. You would see various information like the name of the author,
the date it was commited, a commit SHA number, and the message for the
commit.

You should also see your most recent commit, where you added the two new
files in the previous section.

## Branching

Most large code bases have at least two branches - a ‘live’ branch and a
‘development’ branch. The live branch is code which is OK to be deployed
on to a website, or downloaded by customers. The development branch
allows developers to work on features which might not be bug free. Only
once everyone is happy with the development branch would it be merged
with the live branch.

Creating a branch in Git is easy. The `git branch` command, when used by
itself, will list the branches you currently have

    $ git branch

The `*` should indicate the current branch you are on, which is
`main`.

If you wish to start another branch, use
`git checkout -b (new-branch-name)` :

    $ git checkout -b new-feature

Try git branch again to check which branch you are currently on:

    $ git branch
      new-feature
    * main

The new branch is now created. Now let’s work in that branch. To switch
to the new branch:

    $ git checkout new-feature

`git checkout (branch-name)` is used to switch branches.

Let’s perform some commits now,

    $ echo 'some content' > test.txt
    $ git add test.txt
    $ git commit -m "Add new text"

Now, let’s compare them to the main branch. Use `git diff`

    $ git diff main

Basically what the above output says is that `test.txt` is present on
the `new-feature` branch, but is absent on the `main` branch.

## Now you see me, now you don’t

Git is good enough to handle your files when you switch between
branches. Switch back to the `main` branch

Try switching back to the main branch (Hint: It’s the same command we
used to switch to the new-feature branch above)

Now, where’s our `test.txt` file ?

    $ ls
    README.md  lincon.txt   logan.txt

As you can see the new file you created in the other branch has
disappeared. Not to worry, it is safely tucked away, and will re-appear
when you switch back to that branch.

Now, switch back to the new-feature branch, and check that the `test.txt` is
now present.

## Create your first GitHub repository

A repository (repo) is a place where you would store your code. You were
practising on your very own repo just now in Part 1!

The following <a href="https://help.github.com/articles/create-a-repo">
tutorial</a> will show you how to create a GitHub repo - which you can
then share with others.
