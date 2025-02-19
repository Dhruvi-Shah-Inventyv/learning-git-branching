## Level -1: Rebasing over 9000 times

A commit in a git repository records a snapshot of all the (tracked) files in your directory. It's like a giant copy and paste, but even better!

```bash
git rebase main bugFix
git rebase bugFix side
git rebase side another
git rebase another main
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947651/5_1_bactbj.png)

## Level -2: Multiple Parents

Rather than specifying the number of generations to go back (what ~ takes), the modifier on ^ specifies which parent reference to follow from a merge commit. Remember that merge commits have multiple parents, so the path to choose is ambiguous.

```bash
git rebase main bugFix
git rebase bugFix side
git rebase side another
git rebase another main
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947652/5_2_rp3nn3.png)

## Level -3: Branch Spaghetti

Here we have main that is a few commits ahead of branches one two and three. For whatever reason, we need to update these three other branches with modified versions of the last few commits on main.

Branch one needs a re-ordering of those commits and an exclusion/drop of C5. Branch two just needs a pure reordering of the commits, and three only needs one commit transferred!

```bash
git branch -f three c2
git checkout one
git cherry-pick c4 c3 c2
git checkout two
git cherry-pick c5 c4 c3 c2
```

The below is the ahieved result with this command

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739947652/5_3_gv3s0x.png)

## Completed Level-5

![alt text](https://res.cloudinary.com/dhdyhdvxd/image/upload/v1739948590/level5_o3hugx.png)
