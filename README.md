# bib
Citations seem to be difficult to manage. I will try to solve that with this repo.


https://stackoverflow.com/questions/21353656/merge-git-repo-into-branch-of-another-repo/21353836#21353836

You can't merge a repository into a branch. You can merge a branch from another repository into a branch in your local repository. Assuming that you have two repositories, foo and bar both located in your current directory:


```
$ ls
foo bar
```


Change into the foo repository:
```
$ cd foo
```


Add the bar repository as a remote branch and fetch it:


```
$ git remote add bar ../bar
$ git remote update
```

Create a new branch baz in the foo repository based on whatever your current branch is:


```
$ git checkout -b baz
```


Merge branch somebranch from the bar repository into the current branch:


```
$ git merge --allow-unrelated-histories bar/somebranch
```


(--allow-unrelated-histories is not required prior to git version 2.9)