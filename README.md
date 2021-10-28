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


#### :file_folder: Git States

Git thinks of its data more like a set of snapshots of a miniature filesystem. Every time you commit, or save the state of your project in Git, it basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot.** Git thinks about its data more like a stream of snapshots. **


Everything in Git is check-summed before it is stored and is then referred to by that checksum. This means it’s impossible to change the contents of any file or directory without Git knowing about it.Git stores everything
in its database not by filename but by the hash value of its contents.

Now, pay attention. This is the main thing to remember about Git if you want the rest of your learning process to go
smoothly. ** `Git has three main states that your files can reside in: committed, modified, and staged.` **

>  Committed means that the data is safely stored in your local database.

>  Modified means that you have changed the file but have not committed it to your database yet.

>  Staged means that you have marked a modified file in its current version to go into your next commit snapshot.
	
<img src="https://github.com/MohamedGElsharkawy/GitSheet/blob/main/screenshot/git-states.png" width="500" height="500">	



