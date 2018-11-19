---
title: "Supplemental: Using Branches with Git"
teaching: 10
exercises: 15
questions:
- "What is branches and how to use it ?"
objectives:
- "Understand how to use branches with Git"
keypoints:
- "`git branch` Create branches"
- "`git checkout` Change the branche"
- "`git merge` Merge branches"
- "`git show-branch` Display branches"
---
In very simple terms, git branches are individual projects within a git repository. Different branches within a repository can have completely different files and folders, or it could have everything the same except for some lines of code in a file.

Let’s use a few real world examples (at least that I’ve used before, others may have used them differently):

* Pretend you submitted a research article to a journal and they want you to revise it based on some reviewers comments. There are several ways to deal with the comments, so instead of changing your main manuscript, you create a revision branch in your manuscript git repository. In that branch you make the changes to your manuscript in response to the reviewers. Once you are satisfied, you merge the branch into the master branch and resubmit the article.
* Imagine you have a dataset that multiple people work off of but that is also often updated with more data. You think you found a problem with the dataset, but aren’t sure. So you create a new branch fixing to fix the problems without messing with the master dataset. After you confirm the problem is real and that you have the solution, you submit a pull request of the fixing branch to be merged with the master branch.
* What is often the case in software development, a bug or missing feature in the software gets identified. Because the software is already in production use (fairly stable, other people rely on it, etc), you can’t just make changes to the main software code. So a hotfix or feature branch is created to address these problems, which will eventually get merged in with the master branch for the next version of the software. This ensures that other people’s code isn’t broken everytime a bug gets fixed.

> ## How it works
> The nice (and very powerful) thing about Git is the fact that branches are very cheap compared to other version control systems. By cheap, I mean they don’t take up much disk space, it’s computationally easy to move between branches, and it’s (relatively) easy to merge branches together. This is because of how Git represents branches, since they are simply pointers or an individual commit. That’s it. Just a pointer… Git commit history is a directed acyclic graph, which means that every single commit always has a ‘parent’ commit (the previous commit in the history, or multiple parents when a merge happens), and any individual commit can have multiple ‘children’. 
> This history can be traced back through the ‘lineage’ or ‘ancestry’. The branch just gives a name to each ‘lineage’ when a commit has multiple children.
{: .callout}

When you merge two branches together, the commit histories get merged together as well. Which means that all the changes you made in each branch gets combined back into a single lineage, rather than two. This makes it easier to work collaboratively on a project, since each individual could work on their own branches, without dealing with the messiness that could come from working all on one branch.


## Let's start : Create a new branch

Our `mars.txt` file
~~~
$ cat mars.txt
~~~
{: .language-bash}
~~~
Cold and dry, but everything is my favorite color
The two moons may be a problem for Wolfman
But the Mummy will appreciate the lack of humidity
An ill-considered change
~~~
{: .output}

Create a new branche named `rocket`
~~~
$ git branch rocket
~~~
{: .language-bash}

So far nothing really appends :
~~~
$ git status
~~~
{: .language-bash}
~~~
On branch master
nothing to commit, working tree clean
~~~
{: .output}

We need to change the branch
~~~
$ git checkout rocket
~~~
{: .language-bash}
~~~
Switched to branch 'rocket'
~~~
{: .output}

We can edit the `mars.txt` file and add something about the rocket project
~~~
$ nano mars.txt
$ cat mars.txt
~~~
{: .language-bash}
~~~
Cold and dry, but everything is my favorite color
The two moons may be a problem for Wolfman
But the Mummy will appreciate the lack of humidity
An ill-considered change


The project of rocket will need a spaceship and a motor
Father might have the budget for it
We need to also to move material and animals
~~~
{: .output}



Then we add and commit changes
~~~
$ git status
~~~
{: .language-bash}
~~~
On branch rocket
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   mars.txt

no changes added to commit (use "git add" and/or "git commit -a")
~~~
{: .output}

~~~
$ git add mars.txt
$ git commit -m "start the rocket project"
~~~
{: .language-bash}
~~~
[rocket 468dd5c] start the rocket project
 1 file changed, 6 insertions(+)
~~~
{: .output}

This modification only affected the `rocket` branch if we go back to the `master` branch the `mars.txt` file is unchanged.
~~~
$ git checkout master
$ cat mars.txt
~~~
{: .language-bash}
~~~
Cold and dry, but everything is my favorite color
The two moons may be a problem for Wolfman
But the Mummy will appreciate the lack of humidity
An ill-considered change
~~~
{: .output}

Branches are useful tools for working on different version of a project and to switch back and forth to it.

## Merging branche

Merging branches means to include the change of one branch to another.

We go to the destination branch (`master`here)
~~~
$ git checkout master
~~~
{: .language-bash}
~~~
Switched to branch 'master'
~~~
{: .output}

And we merche `rocket`branch into it
~~~
$ git merge rocket
~~~
{: .language-bash}
~~~
Updating dbd9912..468dd5c
Fast-forward
 mars.txt | 6 ++++++
 1 file changed, 6 insertions(+)
 ~~~
{: .output}

`mars.txt` changed 

~~~
$ cat mars.txt
~~~
{: .language-bash}
~~~
Cold and dry, but everything is my favorite color
The two moons may be a problem for Wolfman
But the Mummy will appreciate the lack of humidity
An ill-considered change


The project of rocket will need a spaceship and a motor
Father might have the budget for it
We need to also to move material and animals
~~~
{: .output}


you can delete the `rocker`branch

~~~
$ git branch -D rocket
~~~
{: .language-bash}
~~~
Deleted branch rocket (was 468dd5c).
~~~
{: .output}



