## Level -1: Git commits

A commit in a git repository records a snapshot of all the (tracked) files in your directory. It's like a giant copy and paste, but even better!

```bash
git commit
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947650/1_1_result_g8d0cj.png)

## Level -2: Branching in Git

Branches in Git are incredibly lightweight as well. They are simply pointers to a specific commit -- nothing more.
Because there is no storage / memory overhead with making many branches, it's easier to logically divide up your work than have big beefy branches.

```bash
git branch bugFix
git checkout bugFix
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947650/1_2_result_fpmmo8.png)

## Level -3: Merging in Git

The first method to combine work that we will examine is git merge. Merging in Git creates a special commit that has two unique parents. A commit with two parents essentially means "I want to include all the work from this parent over here and this one over here, and the set of all their parents."

```bash
git checkout -b bugFix
git commit
git checkout main
git commit
git merge bugFix
```

The below is the ahieved result with this command
``![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947650/1_3_result_uweb67.png)

## Level -4: Git Rebase Introduction

The second way of combining work between branches is rebasing. Rebasing essentially takes a set of commits, "copies" them, and plops them down somewhere else.

```bash
git checkout -b bugFix
git commit
git checkout main
git commit
git checkout bugFix
git rebase main
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947650/1_4_result_jsnkt4.png)
