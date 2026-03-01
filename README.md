## Merge vs Rebase
* The Git --distributed-is-the-new-centralized 
* Based on new requirement a freature brach is created to add the new lines of code full the defined requirement in increamental steps.
* Each change is add to the staging area (git add) and commited the feature branch with unique commit id (git commit -m "The feature is implemented")
* once all the conditions are meet. The Pull request (PR) is created by developer to merge the code to main/target branch

### In order to merge the code. The fulling basic conditions should be meet:
* User have to login to github/bitbucket or any remote console
* select the target branch to which the feature branch has to merged
* describe what are new features added to the code in PR description and create PR
* once all developer or team members agree upon the changes and approve the merge request
* The developer created the PR can merge the code to target branch
## Pull request can be of three types:
* Merge: creates a extra commit id to merge commit that has two parent commits
    - one from feature/current branch and one from branch to which branch is merged 
* Rebase: 
Rebasing is a process of moving or combining a sequence of commits to a new base commit. It allows you to take the changes from one branch and reapply them on top of another branch

### feature-1

* Devloper X has add this line of code
* * X spend some y time to implement this feature
* * To merge the feature-1 to main here we used merge strategy. 
* * creates an extra commit for merge request which always have two parent commit ids
* * it maintains a chain structure


## rebase-branch

* Devloper YZ has implemented API to query the stock inverntory from remote
* feature 2 requirement is fulfilled
* Rebase merge strategy is used to merge the code
* rewrites the history with new commit id's and hides the author details of commit's history before merge
* maintians linear history of records


