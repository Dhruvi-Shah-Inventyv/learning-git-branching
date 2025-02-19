## Level -1: Cherry pick intro

The first command in this series is called git cherry-pick. It takes on the following form:

git cherry-pick <Commit1> <Commit2> <...>
It's a very straightforward way of saying that you would like to copy a series of commits below your current location (HEAD). I personally love cherry-pick because there is very little magic involved and it's easy to understand.

```bash
git cherry-pick c3 c4 c7
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947651/3_1_result_xcrml5.png)

## Level -2: Interactive rebase intro

Git cherry-pick is great when you know which commits you want (and you know their corresponding hashes) -- it's hard to beat the simplicity it provides.
All interactive rebase means is that Git is using the rebase command with the -i option.

If you include this option, git will open up a UI to show you which commits are about to be copied below the target of the rebase. It also shows their commit hashes and messages, which is great for getting a bearing on what's what.

```bash
git rebase -i c1
```

The below is the ahieved result with this command
![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947651/3_2_result_octmax.png)

## Completed Level-3

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739948589/level3_ipyacz.png)
