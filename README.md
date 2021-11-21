# GitSheet
This repo demonstrates the playing journey with  **`Git`** commands  :rocket:


# Getting Started 

Here we are sharing with you how to play with git commands :memo:, thoughts, challenges, resources, and other stuff that will be interested for you. :monocle_face: :bulb: :star:


# Introduction

### - 📅 History

 Before we dip into `Git`, we have to discuss an overview and history about version control. 

* 🗒️ In the 90's, Microsoft introduced VSS (Visual SourceSave).It’s a client/server system. The server stores a database of all project files together with the history of changes for these files

   > `VSS` allows you to manage multiple developers on the same project, by “checking out” a file from the server, so this process allows the developer    when working on a file to prevent changes from other developers till he makes a check out for this file.

 * 🗒️ After `VSS`, `SVN (SubVersion)` was launched as a version control system, and introduced a command line interface.

   > `SVN` tackling another issue called “Tree conflict”, that caused by a conflict when multiple developer working on the same directory,and SVN doesn’t allowed to commit with these conflicts 

* 🗒️ With `SVN` and `VSS`, Microsoft went ahead with a new version control, `TFS (Team Foundation Server)`, which enabled to work with `Checking out file system as  VSS`, or `Branching model as SVN`.

* 🗒️ In the meantime, `Git` was introduced with a powerful merging model, and as a  distributed version control, not like `VSS / SVN`  which working as a client/server system, so no need to be connected to a server.


#### 📝 Why is version control important ?
 
> It’s so important to keep everything in source control for delivery process, and a single source of truth.


- Keep tracking of changes
- Helps team collaborate 
- Working on versioning and history 
- Manage traceability , who/when do these changes


#### :file_folder: Types of changes on Git

- Add  file
- Delete file
- Edit file
- Rename file


#### :construction: When you get a conflict ?

* When multiple users trying to edit the same line in a file, as shown below 

	- User1 trying to add `½ tbsp cilantro`, and User2 trying to add `2 tbsp cilantro` in the same line
* Or when User1 delete a file, User2 trying to edit/modify the same file
* > So, you have to keep your files updated with latest changes from remote `GIT SERVER`

<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/conflict.png" width="500" height="350">


### :file_folder: Git States

Git thinks of its data more like a set of snapshots of a miniature filesystem. Every time you commit, or save the state of your project in Git, it basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot.**Git thinks about its data more like a stream of snapshots.**


Everything in Git is check-summed before it is stored and is then referred to by that checksum. This means it’s impossible to change the contents of any file or directory without Git knowing about it.Git stores everything
in its database not by filename but by the hash value of its contents.

Now, pay attention. This is the main thing to remember about Git if you want the rest of your learning process to go
smoothly. **`Git has three main states that your files can reside in: committed, modified, and staged.`**

>  Committed means that the data is safely stored in your local database.

>  Modified means that you have changed the file but have not committed it to your database yet.

>  Staged means that you have marked a modified file in its current version to go into your next commit snapshot.
	
<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/git-states.png" width="500" height="500">	

* **Working Directory**

	> It is your current local directory that you are working on. It's a signle checkout of one version of the project
	
	There are types of states in working directory 
	
 	> **Tracked files** : are files that were in the last snapshot; they can be unmodified, modified, or staged. 
	
  	> **Untracked files** : are everything else—any files in your working directory that were not in your last snapshot and are not in your staging area.
	 
	 
* **Staging Area**

	> It is a file, generally in your `Git Directory`, stores information about what will go on your next commit, It's 
	someetimes referred to as the `Index`

* **Git Directory**
	> It is where git stores the metadata and object database of your project.

### :cloud: Git Remote

 We have discussed before, there is a git directory on your device where you store object and metadata for your git, for example:
   - Staging area
   - local database (Your local repository)
   - Remote database (A copy of your remote repository)
	
So, for working with any remote repository on any cloud service `ex: Github`, you should create a copy of that remote in your git directory.

   - This copy of remote on your local device, it's working as `tracking` for the remote on cloud 
   - As for remote one, it's your `upstream`
	
So, let's recap that scenario how it will work
   - You have a remote upstream repository (Stored on cloud)
   - You have a tracking copy connected with that upstream remote (Stored on local)
   - You have a local database connected with the tracking copy (Stored on local)

> You can set any name for that copy of tracking remote, the default name is `origin`.

> You have to set upstream for each branch on remote to connect with local remote.

 <p align="center">
	<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/upstream.png" width="500" height="500">	
</p>

		
### :memo: Git Basics Overview 

- **Repository**
  > It contains all your necessary repository files—a Git repository skeleton.


- **Cloning** 
  > This will create your copy of an existing Git Repository 


- **Status**
  > To determine which files are in which state 

<p align="center">
	<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/file_state.png" width="500" height="300">	
</p>

- **Commit** 
  > It’s a group of changes and it has only the changes, each commit points to parent commit(s).


- **Branch**
  > It’s the duplications of all commits as an object, the branch isolate the new commits while keeping pointing to parent      commit(s) before the isolation

<p align="center">
<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/branch.png" width="250" height="250">	
</p>		


- **head and HEAD**

    There are two types of references for commit/branch:

	 > head : is a reference for a commit object, it has a name (branch name , tag name ..), the last commit from each branch represents the head for branch.

	 > HEAD (CAPITAL LETTERS): is an active / current head, points to commit you are working on.
 
 
- **Merge**

   The merge have some types, so let’s represent with these visualizations:


	- Non Fast Forward (have two parents)
		> In case you have new commits added after the last isolation feature branch, in this case you create a new commit representing the two branches, and the HEAD (active/current head) move to refer to this new commit.

	 <p align="center">
	<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/nonff.png" width="250" height="250">	
	</p>


	- Fast Forward (have one parent)
		> In case you have not any new commits added after the last isolation feature branch, in this case you make the HEAD (active/current head) move to refer to the last commit in the isolation feature branch.

	 <p align="center">
	<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/ff.png" width="250" height="250">	
	</p>


	- Rebase
		> You will copy/rewrite all the new commits of the feature branch and merge them into the existing branch.


	 <p align="center">
	<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/rebase.png" width="250" height="250">	
	</p>


	- Squash
		> You can represent it as combining all the new added commits in the isolation feature branch into one single commit, then merge this commit to the existing branch.


	 <p align="center">
	<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/squash.png" width="250" height="250">	
	</p>

	
