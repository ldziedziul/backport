# backport

This tool backports the latest commit pointed by <source-ref> on the top of <target-branch> by crating a new branch.
Then it pushes the newly created branch and creates a new PR.

```
Usage: 
backport <source-ref> <target-branch> [-c | --continue] [-l | --local]

Options:
  -l, --local    Skip pushing the branch and creating the PR
  -c, --continue Continue backporting after fixing cherry-pick conflict

What does it do:
   'backport master upstream/5.2.z' - will perform the following actions:
    - create a new branch from upstream/5.2.z
    - cherry-pick the latest commit from master and append its message with ' [5.2.z]'
    - push the new branch to origin
    - create a PR from the new branch to 5.2.z branch and copies labels from the original PR (if found)
```
