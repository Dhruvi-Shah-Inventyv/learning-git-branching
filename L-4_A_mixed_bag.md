## Level -1: Grabbing Just 1 Commit

Here's a development situation that often happens: I'm trying to track down a bug but it is quite elusive. In order to aid in my detective work, I put in a few debug commands and a few print statements.

All of these debugging / print statements are in their own commits. Finally I track down the bug, fix it, and rejoice!

Only problem is that I now need to get my bugFix back into the main branch. If I simply fast-forwarded main, then main would get all my debug statements which is undesirable. There has to be another way...

We need to tell git to copy only one of the commits over. This is just like the levels earlier on moving work around -- we can use the same commands:

```bash
git rebase -i
git cherry-pick
```

The command we used to reach the goal:

```bash
git rebase -i c1
git branch -f main
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947651/4_1_omlbwy.png)

## Level -2: Juggling commits-1

Here's another situation that happens quite commonly. You have some changes (newImage) and another set of changes (caption) that are related, so they are stacked on top of each other in your repository (aka one after another).

The tricky thing is that sometimes you need to make a small modification to an earlier commit. In this case, design wants us to change the dimensions of newImage slightly, even though that commit is way back in our history!!

We will overcome this difficulty by doing the following:

We will re-order the commits so the one we want to change is on top with git rebase -i
We will git commit --amend to make the slight modification
Then we will re-order the commits back to how they were previously with git rebase -i
Finally, we will move main to this updated part of the tree to finish the level (via the method of your choosing)

```bash
git rebase -i c1
git rebase -i c3'
git rebase -i c1
git branch -f main c3''
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739948215/4_2_wdgwd9.png)

## Level -3: Juggling commits-2

Here's another situation that happens quite commonly. You have some changes (newImage) and another set of changes (caption) that are related, so they are stacked on top of each other in your repository (aka one after another).

The tricky thing is that sometimes you need to make a small modification to an earlier commit. In this case, design wants us to change the dimensions of newImage slightly, even though that commit is way back in our history!!

We will overcome this difficulty by doing the following:

We will re-order the commits so the one we want to change is on top with git rebase -i
We will git commit --amend to make the slight modification
Then we will re-order the commits back to how they were previously with git rebase -i
Finally, we will move main to this updated part of the tree to finish the level (via the method of your choosing)

```bash
git checkout main
git cherry-pick C2
git commit --amend
git cherry-pick C3
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947651/4_3_gka6jj.png)

## Level -4: Git tags

If that's the case, you may be wondering if there's a way to permanently mark historical points in your project's history. For things like major releases and big merges, is there any way to mark these commits with something more permanent than a branch?

You bet there is! Git tags support this exact use case -- they (somewhat) permanently mark certain commits as "milestones" that you can then reference like a branch.

More importantly though, they never move as more commits are created. You can't "check out" a tag and then complete work on that tag -- tags exist as anchors in the commit tree that designate certain spots.

```bash
git tag v0 c1
git tag v1 c2
git checkout c2
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739948303/4_4_a9ix1x.png)

## Level -5: Git describe

If that's the case, you may be wondering if there's a way to permanently mark historical points in your project's history. For things like major releases and big merges, is there any way to mark these commits with something more permanent than a branch?

You bet there is! Git tags support this exact use case -- they (somewhat) permanently mark certain commits as "milestones" that you can then reference like a branch.

More importantly though, they never move as more commits are created. You can't "check out" a tag and then complete work on that tag -- tags exist as anchors in the commit tree that designate certain spots.

```bash
git describe main
v0_2_gC2
git describe side
v1_1_gC4
git describe bugFix
v1_2_gC6
git commit
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947651/4_5_hfwtev.png)

## Completed Level-4

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739948590/level4_hzswus.png)
