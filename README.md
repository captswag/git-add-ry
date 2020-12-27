## Quick reference


### 1. Chapter - The Basics

```
git log --online
```

Condenses each commit information of `git log` to a single line.

```
git log --oneline <file-name>
```

Displays the history of `<file-name>` (all the commits after `<file-name>` is added to git).

### 2. Chapter - Undoing Changes

```
git tag -a <tag-name> -m "<description>"
```

Create an annotated tag pointing to the most recent commit. (`git checkout <tag-name>`).

```
git reset --hard
```

Reset tracked files (both working directory and staging area changes) to the most recent commit.

```
git clean -f
```

Remove untracked files.

### 3. Chapter - Branches I

The HEAD is Git's internal way of indicating the snapshot that is currently checkout out. The HEAD normally resides on 
the tip of the development branch.

```
git branch <branch-name>
```

Creates a new branch using the current working directory as its base.

```
git merge <branch-name>
```

Merge a branch into the checked-out branch.

##### Fast-forward merge

![before-merge](images/branches-i-before-merge.png)

```
git merge css
```

![after-merge](images/branches-i-after-merge.png)

Instead of re-creating the commits in css and adding them to the history of `master`, Git reuses the existing snapshot 
and simply moves the tip of `master` to match the tip of `css`. This kind of merge is called fast-forward merge, since 
Git is "fast-forwarding" through the new commits in the `css` branch.

### 4. Chapter - Branches II

Temporary branches are called topic branches because they exist to develop a certain topic, then they are deleted.

Longer-running type of topic branches are called a feature branch as it was created with the intention of developing a 
specific feature.

Hotfix branches are used to quickly patch a production release.

Usually permanent master branch is used as a foundation for all these temporary branches. In addition to master, many 
programmers add a second permanent branch called develop. This lets them use master to record really stable snapshots 
(e.g., public releases) and use develop as more of a preparation area for master.

```
git commit -a -m "<message>"
```

Stage all tracked files and commit the snapshot using the specified message.

##### 3-way merge

![before-merge](images/branches-ii-before-merge.png)

```
git merge master
```

![before-merge](images/branches-ii-after-merge.png)

A 3-way merge occurs when you try to merge two branches whose history has diverged. It creates an extra merge commit 
to function as a link between the two branches. As a result, it has two parent commits.

### Chapter 5 - Rebasing