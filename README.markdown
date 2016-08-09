Tall Tales and Reverts
======================

We've started collecting
------------------------

We've started collecting tall tales about famous Physicists, the only problem is that some of them are impossible to verify!

We'll have to get rid of the commits that add those stories, In order to do that we're going to try a few different options.

The commits
-----------
There are several commits in order, we've been careful and have only added one scientist at a time to our timeline.
Unfortunately the story about George Gamow isn't verifiable (the horror!) so we're going to have to get rid of it.

The default method
------------------
1. Delete the story from the file.
2. Make a new commit.

That's fine but...
------------------
Sometimes that's not practical, like if there's a commit with thousands of changes. In that case we'll have to know how to get git to do our dirty work.

First we'll need to find out which commit added the story, then we'll need to undo or remove that commit somehow.

We're going to try out a few different ways, before you try each method you may want to check out a new branch (eg. `git checkout -b revert_tall_tales`) so you can return to this example afterwards.

Alternatively you can always create a new branch from the reference origin/revert

The Revert method
-----------------
1. Find the commit that added the story about George Gamow.
2. Use `git revert <commithash>` to revert the commit
3. Your revert is going to cause a merge conflict since the file has been changed in the same place since we wrote the George Gamow story. Resolve this conflict just like in the merging tutorial.
4. To see your options run `git status`. Basically you can either abort or continue.
5. After you've fixed the conflict run `git add <file>` to tell git the change to make, then run `git revert --continue` to apply the revert commit.
6. We're done! But we also have a revert commit in our history and we had to do some manual work, if we're working on a branch we haven't shared with anyone else we can clean up our history/hide our mistake.

The cherry-pick method
----------------------
1. Get a list of the commits after the George Gamow story commit, these are the commits that we're going to want to cherry-pick
2. Find the commit that is the parent of the George Gamow story commit.
3. Make a new branch based on this starting commit, you can do that by checking out the commit and then checking out a new branch.
4. cherry-pick each commit in your list in the order you want them to appear
5. We're done! But that was a lot of work...

The interactive rebase method
-----------------------------
This is the most complex but powerful of these methods, you may want to do this a few times and try out all of the options it gives you. The basic method goes like this:

1. As before we need to find the commit that is the parent of the George Gamow story commit.
2. Run `git rebase --interactive <commithash>`
3. You're going to get a list of commits, these are the commits that are going to be applied sequentially to the base sha.
4. Delete the line with the George Gamow commit in it.
5. Save and exit. The commits should apply in order.


Congrats!
---------
You've done some of the most difficult things that teams have to do with git. Take a look at your `git reflog` and try to trace back all of the changes you made :)

Author
------

This work is licensed under the Creative Commons
Attribution-NonCommercial-ShareAlike 3.0 License\
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">http://creativecommons.org/licenses/by-nc-sa/3.0/</a>\
Author: Thong Kuah\
Contributors: Nick Malcolm, Andy Newport
