## GIT COMMANDS
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
[![HitCount](https://hits.dwyl.com/joelts/git-commands.svg)](https://hits.dwyl.com/joelts/git-commands)

### Basic
- CLEAR GIT BASH SCREEN : `clear`
- LIST ALL BRANCHES : `git branch -a`
- OPEN FILE TO EDIT : `vi <file_name>`  // [vi `visual editor` in UNIX](https://www.geeksforgeeks.org/vi-editor-unix/)
- ADD NEW FILE : `touch <file_name>.<extension>`
- ADD FILE CONTENT : `echo "<content>" >> <file_name>`
- UPDATE GIT : `git update-git-for-windows`
- CREATE BRANCH : `git branch <branch_name>`
- SWITCH BRANCH : `git checkout <branch_name>`
- LIST CONFIG : `git config --list`
- LIST FILES : `ls -lrt`
- LIST STAGED FILE ONLY : `git ls-files --stage`
- PUSH TO REMOTE : `git push --set-upstream origin <current_branch_name>`
- CREATE NEW FOLDER : mkdir <folder_name>
- VIEW DIFFERENCES (working dir and staging) :  // Mainly used while Merging Branches
  - `git diff <file_name>` // file versions
  - `git diff <branch_name>` // branch
  - `git diff master..<branch_name>` // between master and feature branch  
- CHECK FILE DIFF (staging and last commited) : `git diff --staged`
- SET NOTEPAD AS DEFAULT EDITOR : `git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"`
- DELETE A FILE : `git rm <file_name>`
- RENAME A FILE : `git mv <file_name> <new_file_name>`
- LIST PREVIOUS COMMITS AND IDS (one line) : `git log --oneline` OR `git log --oneline --decorate --graph`
- VIEW FILE CONTENT : `cat <file_name>`
- CHECK PREVIOUS VERSION OF FILE : `git checkout <commit_id> <file_name>`
- MODIFY RECENT COMMIT : `git commit --amend`
- REMOVE FILE FROM LAST COMMIT : `git rm -- cached <file_name>`
- RENAME BRANCH : `git branch -m <old_name> <new_name>`
- TO VIEW CHANGES : `git whatchanged -since = '2 weeks ago'`
- VIEW CHANGES DONE BY YOU : `git reflog`
- GO BACK TO OLD COMMIT: `git reset HEAD@{index}`
- VIEW BRANCH BY COMMIT : `git branch --contains <commit_id>`
- CREATE NEW BRANCH AND SWITCH (at once) : `git branch -b checkout <new_branch_name>`
- MERGE BRANCH : `git merge <branch_name>`  // Switch to <branch_name>, NOT `master` branch !! // After MERGE there is no differences found.
- NEW BRANCH : `git branch <new_branch_name>`
- SWITCH BRANCH : `git checkout <branch_name>`
- LIST BRANCHES : `git branch`
- SYNC REMOTE AND LOCAL REPO : `git pull origin master`
- VIEW ALL DIFFERENCES - `git diff` // **GIT GUI** can also be used for viewing differences pictorially.


### MERGING
- GIT MERGE ALGORITHMS : Fast Forward Merge and Recursive Merge
- FAST FORWARD MERGE : Instead of creating a new commit, `MASTER` branch just points towards the last commit of the feature(can be any branch) branch. This is used when there is just commit/s in the `feature` branch.
- RECURSIVE MERGE : This is the default git merge.  Create a new commit (say X) and `MASTER` branch points towards X. This is used when there are commits in both `MASTER` and `feature` branches at the time of merging.


### STASHING
- COMMANDS :-
  - `git stash` Records the current state and revert to the last commit (clean working tree), withot inmterrupting the current work.
  - `git stash save "<stash_message_here>"` Stash with a message
  - `git stash list` Shows the list of previous stashes along with the associated message (if any). 
  - `git stash apply` Takes a stashed change and applies it to your current working tree (also leaving it on the “stash stack”).
  - `git stash pop command` Remove a slash snapshot from slash list.
  - `git stash show` Display the number of files involved in stash and lines updated.
  - `git stash clear` To clear the stash and empty.
![git_stash](https://user-images.githubusercontent.com/47276398/116804762-15aed200-ab3f-11eb-9840-b4b0ea8e6922.jpg)


### SQUASH COMMITS ON A BRANCH (One-way of doing it)
- `git checkout <your-branch-having-changes>`
- Rebase (Pick first commit and replace 'pick' with 'f' for below commits) :
  - Master branch - `git rebase -i master` 
  - Same branch   - `git rebase -i HEAD~<number_of_commits>` 
- `git commit --amend` OPTIONAL : If commit message needs to be updated
- `git push --force-with-lease`


### DELETE PREVIOUS COMMIT/S
- `git reset --hard HEAD~1` Deletes previous commit(1)
- `git push --force-with-lease`


### REBASING 
- This is a process of moving a branch to a different commmit.
- COMMANDS :-
  - `git rebase master` Rebase the current branch to the latest commit in master. Apply from the feature branch NOT master branch !!

***NOTE*** : Never use `git rebase` on public branches.


### ADDING LARGE FILES (file size greater than 25 mb)
[Click Here](https://ayunascode.medium.com/how-to-push-large-files-to-github-253d05cc6a09)



*Author* : `Joel T Samuel`