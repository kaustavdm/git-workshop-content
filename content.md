What is a Version Controlling System?
-------------------------------------

A Version Controlling System (VCS), also called a Revision Control System, keeps track of changes/revisions made to files over a period of time.

VCSs are widely used in software development to track changes to source code.

It becomes highly useful in scenarios where multiple contributors work on the same piece of software.

VCSs store information of who made which changes to which file and when.

A VCS however is not limited to the domain of software developent only, as popularly mis-believed.

VCSs can be used for documentation projects, writing stories, books, articles, lyrics or any type of file.

VCSs are best suited for text files - like source codes, documentations etc. But, they can work with binary files as well - e.g. images, music, video etc. Certain features, like checking differences between revisions can be used with text files only.

In this workshop we will help you learn the basics of a popular VCS called Git. We will cover important aspects of the Git version control system which will help you to begin using Git for your daily work.

But before we begin a hands on training, we need to clarify some conceptual and background information on VCSs.

---- Check for questions ----

Types of VCS
------------

Based on the method of storing information and the user's interaction with the VCS, VCSs are classified into two broad categories: Centralised Version Control Systems (CVCS) and Distributed Version Control Systems (DVCS)

In a CVCS, all information is stored in a central server and a person using that system needs to be connected to that server while saving any changes.

The entire history of the project, all files etc. are stored on the central server. A client (the user here) checks out a copy of that project and submits any change to the server.

As all the history is on the server, to see the history of the project, the user will have to query the central server.

The immediate disadvantage we see here is the need to remain connected to the central server whenever you need to work.

Popular examples of CVCS include Subversion, CVS, Perforce etc.

By contrast, a DVCS is more of a peer-based concept.

Each peer (user) has a full copy of the project, including the project history and the files.

Whenever a user wants they can go through the project history, revert back to old revisions, change existing project content.

Most importantly, a user using DVCS can make and save changes locally without being connected over the network to any other peers or any server hosting a copy of that project.

Whenever the user gets network access, they can push their saved changes to remote peers or to a remote server that stores a copy of that project.

As there is no need of running a separate server for working with DVCS, they are easier to maintain and can be used in various kinds of workflows.

Git is a DVCS. Other widely used DVCSs include Mercurial and Bazaar.

In this workshop, we focus on git.

---- Check for questions ----

Why git?

Git is known for its *reliability* in data storage and its *speed* in committing transactions and retrieving data.

It was originally developed by Linus Torvalds as the VCS for the Linux kernel project. Today Git is heavily developed by a wide pool of developers across the world.

The Linux kernel itself is one of the oldest, largest and most well-kept git project. Many other popular Free Software/Open Source projects use git, e.g. Mozilla, Python etc.

Speed and flexibility are the two main factors that make git stand out from other VCSs.

Making changes and saving a change are extremely fast in git, even in a large project and for a large changeset.

Users of Subversion or even Bazaar will find git to be fitted with two Saturn V rockets.

Git is not just for software developers. It is useful for daily use in collaboratively editing important documents as well.

e.g. any student doing some research can keep track of research-related documents, research papers etc in Git and, thus, keep a history of the entire research project.

Given its flexibility, git can be adapted to wildly different types of workflows.

If there are only a couple of people working on a project, they can pull in changes from and push their changes to each other.

Git can also be used to emulate the workflow popularized by CVCSs where a central server stores a copy of the project. All contributors pull in changes from and merge their changes back to the central server. This workflow is particularly useful for teams with a good number of members.

With some training and practise, you can bend git to your will, without having it the other way round.

Here is a cheat sheet that you can use to lookup useful syntaxes: http://www.git-tower.com/files/cheatsheet/Git_Cheat_Sheet_grey.pdf

Keep it with you. You will find it useful during the workshop.

---- Check for questions ----

Terminologies
-------------

Let us get acquainted with some common and useful terminologies in git and VCS in general. These concepts will help you later on in understanding how git operates.

A *repository* (often called "repo") is simply a git "project". It stores all project history, files and different branches. It is basically a directory with all information within it. Each VCS have their own format of storing histories. In git, repository content is stored in ".git" subfolders.

Repositories in git can be with working tree or be bare.

A *working tree* is a state of the repository where all files in the repository are available for editing on the disk. Those files within the repository directory can be edited, and their changes are saved within the ".git" folder within the repository.

Changes cannot be pushed to a repository with a working tree checked out, that is, when files are in an extracted state, ready to be edited locally.

For this, we need a *bare* repository. A bare repository is basically just the ".git" directory. It stores entire project history and all project files in a compressed binary form. Those files can be extracted (checked out) into a working tree whenever required.

Repositories on central server are always stored in bare format.

Changes saved in a repository are called *commits* in git. Commits in git are permanent snapshots of particular states of the repository.

Sending changes to a remote repository is called *pushing*, while fetching changes from remote repository is called *pulling*.

---- Check for questions ----

A *branch* is a particular flow of history within the repository. e.g. There can be a branch for bleeding-edge/latest development in a repository, while there can be another branch with stable changes only.

All work in that case is done in the development branch and, when stable, is *merged* with the master (stable) branch.

The default branch's name in git is "master".

Basically, branches let you work on different portions of the same repository at the same time without affecting the rest of the repository.

---- Check for questions ----

*Merge* is needed when multiple different changes have been done in different branches. e.g. in a repository of a documentation project, A has edited the README file, while B has edited the LICENSE file. They have made their changes in separate branches. Now in order to get both A's and B's changes into the master branch, we will have to merge each branch with master.

At times there can be changes to the same portion of file by different people. This can result in a *merge conflict*. Conflicts can be resolved pretty easily in git and the repository owner can choose which portion of the change to accept and which one to reject.

However, sometimes there are significant changes made separately in different branches which cannot be merged together any more. Those branches are said to have *diverged* from one another.

Changes between different branches, or between different commits, or between the last commit and any unsaved changes can be seen using *diff*. Diff == Difference.

---- Check for questions ----

Copying an existing repository is called *cloning*.

A *remote* repository is a copy of the same repository in another location. It can be on a different computer or on the same computer in a different location.

In Git, remotes are basically URLs pointing to remote copies of the repository. Each remote is identified by a name so that you don't have to remember the full URL everytime.

When cloning a remote repository, a reference to the remote repository is stored by default with the name of "origin".

In VCS-speak, we refer remote repositories from where you fetch changes as "upstream".

---- Check for questions ----

A *fork* is usually described as a clone of an existing repository, which is taken as a starting point of creating something different from the original repository.

It is not the same as a development branch, but an entirely new repository which is free to go its own way without staying in touch with the original upstream repository.

If a fork has not diverged too much from its upstream, changes from upstream can still be merged into the fork from time to time, and changes in the fork and be submitted upstream as well.

---- Check for questions -----

That is all about the conceptual part for now. If you have any questions, please ask now or hold it till the end of the workshop. Now, satabdi will take over and introduce you to some basic operations in git.
