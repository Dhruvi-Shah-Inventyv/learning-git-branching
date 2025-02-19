## Level -1: Detach HEAD

HEAD is the symbolic name for the currently checked out commit -- it's essentially what commit you're working on top of.

HEAD always points to the most recent commit which is reflected in the working tree. Most git commands which make changes to the working tree will start by changing HEAD.

```bash
git checkout c4
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947650/2_1_result_i4tra0.png)

## Level -2: Relative Refs

With relative refs, you can start somewhere memorable (like the branch bugFix or HEAD) and work from there.

Relative commits are powerful, but we will introduce two simple ones here:

Moving upwards one commit at a time with ^
Moving upwards a number of times with ~<num>

```bash
git checkout HEAD^
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947650/2_2_result_y3psn9.png)

## Level -3: Relative Refs#2

Say you want to move a lot of levels up in the commit tree. It might be tedious to type ^ several times, so Git also has the tilde (~) operator.

The tilde operator (optionally) takes in a trailing number that specifies the number of parents you would like to ascend. Let's see it in action.

```bash
git branch -f main C6
git checkout HEAD~1
git branch -f bugFix HEAD~1
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947651/2_3_result_aq5s7s.png)

## Level-4: Reversing changes in Git

There are two primary ways to undo changes in Git -- one is using git reset and the other is using git revert.

git reset reverses changes by moving a branch reference backwards in time to an older commit. In this sense you can think of it as "rewriting history;" git reset will move a branch backwards as if the commit had never been made in the first place.

```bash
git reset HEAD~1
git checkout pushed
git revert HEAD
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739948451/2_4_ikhiuh.png)

## Completed Level-2

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739948589/level2_roj1pe.png)
