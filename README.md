## Quick reference


### Chapter - The Basics

```
git log --online
```

Condenses each commit information of `git log` to a single line.

```
git log --oneline <file-name>
```

Displays the history of `<file-name>` (all the commits after `<file-name>` is added to git).

### Chapter - Undoing Changes

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

### Chapter - Branches I

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
