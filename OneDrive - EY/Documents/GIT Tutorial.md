git --version

git status

git init

.git





gitignore:

A .gitignore file is a simple text file in your Git repository that tells Git which files or folders to ignore (i.e., not track or push).

If we write the name of any file in that git ignore file then that file or folder will not be tracked and it will be ignored even if we use "git add .".

.gitignore only affects untracked files.If a file is already committed, adding it to .gitignore won’t remove it.To stop tracking it, you must run:"git rm --cached filename"





You can have multiple .gitignore files in different subdirectories.



If we use \*.log , Inside get ignore then it will ignore all those files which have extensions .log And that will not be tracked.
If we use /folder , Then it will ignore all the contents inside that folder and it will not be tracked



\# Ignore Python cache

\_\_pycache\_\_/

\*.pyc



\# Ignore environment files

.env



\# Ignore IDE/project settings

.vscode/

.idea/



\# Ignore OS-specific files

.DS\_Store

Thumbs.db



\# Ignore build/compiled files

/build/

\*.o

\*.exe











git init is always run one time per project

.git is a hidden folder to keep history of all files



git add --a   ------------------------> Used to add all the files into the staging



git config user.name   ---------------------->  Used to get the name of the user

git config user.email  ---------------------->  Used to get the email of the user



git branch           -------> Used to know under which branch we are currently, i.e. like master or main branch



git branch -m NEW\_BRANCH\_NAME      --------------->   is used to rename the branch



Whenever we modify an existing file or if we create a new file then we will have to add Those files and then these files get staged. After that we will do commit.



git push origin BRANCH\_NAME       --------------->   is used to push the file to BRANCH\_NAME branch





git push origin main    --------------->   is used to push the file to the "main" branch





ctrl+shify+p





git diff --staged is     ----------------------->  Suppose we make some change and then add and commit again we make some change and again add, Then this command is used to see the difference after committing 1st time and after adding for second time







git commit -a -m "Direct Commit"    ---------------------------->  By this we can do direct staging without doing add





git rm FILE\_NAME        -------------------------------->   Use to delete the file from local directory

git commit -m FILE\_NAME deleted              -------------------------------->   After deleting it has to be commit.



git mv FILE\_NAME NEW\_FILE\_NAME        -------------------------------->   Use to rename the file in local directory





git rm --cached FILE\_NAME      --------------------------------------->   Suppose we are tracking this file previously and we want to untrack them, then we will first have to put the file name into gitignore and then add and commit the gitignore  and then use this command. If we check at git status, Then it may show that the file has been deleted but actually it has not been.





git clone URL FOLDER\_NAME ---------------------------------------->     If we use this command then whatever repository will be downloaded it will be downloaded after creating a folder named FOLDER\_NAME

---

**PS C:\\Users\\NX542NJ> git init**

**PS C:\\Users\\NX542NJ> git add RapidOCR.py**

**PS C:\\Users\\NX542NJ> git status**

**PS C:\\Users\\NX542NJ> git commit -m "First file addition"**

**PS C:\\Users\\NX542NJ> git status**

**PS C:\\Users\\NX542NJ> git remote add origin https://github.com/FaisalRash/First.git**

**PS C:\\Users\\NX542NJ> git remote -v**

**origin  https://github.com/FaisalRash/First.git (fetch)**

**origin  https://github.com/FaisalRash/First.git (push)**

**PS C:\\Users\\NX542NJ> git push origin main**

&nbsp;        \*\*or (For master branch)\*\*


**PS C:\\Users\\NX542NJ> git push origin master**

**If it's not working then try:**

**git push origin main --force**

---

***Pushing code to the new branch:***



**PS C:\\Users\\NX542NJ> git branch**

**PS C:\\Users\\NX542NJ> git branch  NEW\_BRANCH\_NAME**

**PS C:\\Users\\NX542NJ> git checkout -b NEW\_BRANCH\_NAME**

**PS C:\\Users\\NX542NJ> git branch**

**PS C:\\Users\\NX542NJ> git checkout jk**

**PS C:\\Users\\NX542NJ> git branch**

**PS C:\\Users\\NX542NJ> git status**

**PS C:\\Users\\NX542NJ> git add RapidOCR.py**

**PS C:\\Users\\NX542NJ> git commit -m "File modified"**

**PS C:\\Users\\NX542NJ> git push origin jk**









git push -u origin main   -------->  If we use this command by simply adding -u then next time we don't have to write the whole line. We will have to only write "git push" then new file will be uploaded to the same repo. Also -u means set upstream





git checkout OTHER\_BRANCH\_NAME    -------------------> Is used to navigate from present branch to another.



git checkout -b NEW\_BRANCH\_NAME    -------------------> Is used to create new branch and navigate to it.

git branch  NEW\_BRANCH\_NAME    -------------------> Is used to create new branch.



git branch -d BRANCH\_NAME    -------------------> Is used to delete branch.



We cant delete that branch on which we are present.







git checkout -f ------------------------>is a force checkout.

🔹 What it does : Normally, git checkout <branch> (or in newer Git, git switch <branch>) is used to switch branches.

But if you have uncommitted changes in your working directory, Git will stop you from switching to avoid losing work. The -f (or --force) Throw away local changes and forcefully switch.

















Merging Code



Way 1



git diff <- branch name->



git merge <- branch name->



(to compare commits, branches, files \& more)



(to merge 2 branches)



Way 2



Create a PR









Pull Command



git pull origin main    ------------------------------------->   used to fetch and download content from a remote repo and immediately update the local repo to match that content.





---

Merge Conflicts

An event that takes place when Git is unable to automatically resolve differences in code between two commits.





Suppose we have added a new line to the file which is in main branch and added another line into the same line into the same file which is in another branch by using add and commit, Then if we try to merge both branch using "git merge main"(If we are not in main branch then we will use main) then we will get merge conflict.





**PS C:\\Users\\NX542NJ> git add RapidOCR.py**

**PS C:\\Users\\NX542NJ> git commit -m "No added"**



**PS C:\\Users\\NX542NJ> git branch**

**PS C:\\Users\\NX542NJ> git checkout jk**

**PS C:\\Users\\NX542NJ> git add RapidOCR.py**

**PS C:\\Users\\NX542NJ> git commit -m "None added"**

**PS C:\\Users\\NX542NJ> git merge main**



Then we will see some type of conflict in VS code. Then there could be two things we can do:

1). Just remove all the unnecessary lines and then keep only those lines which you have made changes in the previous add and commit.

2). We can click on the button. There are total 4 buttons: first button is "Accept Current Change" will accept only those change which has been made into the 'jk' branch. Then other button is "Accept Incoming Change" which means to accept those changes which are done on the 'main' branch and will come to the 'jk' branch or the third option is accept both changes.



**PS C:\\Users\\NX542NJ> git add RapidOCR.py**

**PS C:\\Users\\NX542NJ> git commit -m "Both added"**

**#PS C:\\Users\\NX542NJ> git merge jk**

**PS C:\\Users\\NX542NJ> git push origin jk**















Undoing Changes



Case 1 : staged changes  (undo add)



git reset FILE\_NAME -------------------> For undo of add for particular file

git reset  -------------------> For undo of add for all file



we can check using "get status" for checking the undo action. We will see "changes not staged for commit:"

with "modified : File\_Name" in red.



Case 2 : commited changes (for one commit)  (undo commit)



git reset HEAD~1



Case 3 : commited changes (for many commits)



git log

git reset COMMIT\_HASH\_CODE --------------------------> will make undo commit upto that particular commit

git reset -- hard COMMIT\_HASH\_CODE  --------------------------> will make undo commit upto that particular commit and changes will be seen in VS Code also







git reset FILE\_NAME  \&   git restore--staged FILE\_NAME  ---------------->  Can do the same function of undoing staging change.





Fork



A fork is a new repository that shares code and visibility settings with the original "upstream" repository. Fork is a rough copy.















git log -p ---------------------> Commit history + exact code changes for each commit. It’s like combining git log and git diff together.When we run git log we get a list of commits: Commit hash (ID), Author, Date, Commit message. But this only shows what commits were made, not what changed inside them.

By adding -p option tells Git: “For each commit, also show me the actual code changes (diff) that the commit introduced.” So instead of just seeing commit messages, you also see the exact lines of code that were added (+) or removed (-). The -p means "patch".





git log -p -1 ----------------→ Show patch for only the latest commit.

git log -p -2 ------------------→ Show patches for the last 2 commits.

git log -p -- hello.txt -----------→ Show patches but only for hello.txt.





git log --stat  -------------------------------> is similar to git log -p, but instead of showing the full patch/diff, it shows a summary of changes made in each commit.

git log --stat -2 ---------------------------------→ Show stats for the last 2 commits.

git log --stat -- README.md ----------------------→ Show stats but only for changes in README.md.

git show --stat <commit\_hash> ---------------------→ Show stats for a specific commit.





git log --pretty=oneline = Clean, one-line history view of your commits. Useful when you just want an overview of commits without details.





git log --since=2.days----------------------------->Show all commits made in the last 2 days.

git log --since=2.weeks----------------------------->Show all commits made in the last 2 weeks.

git log --since=2.months----------------------------->Show all commits made in the last 2 months.

git log --since="2025-09-20" ----------------------→ All commits since Sept 20, 2025.

git log --since="yesterday" ------------------------→ All commits from yesterday onwards.

git log --since="2 weeks ago" ---------------------→ Commits in the last 2 weeks.

git log --since="2025-09-01 10:00" ---------------------→ Commits since a specific date \& time.

git log --since="2025-09-20" --until="2025-09-23"   -------------------------> Shows commits between Sept 20 and Sept 23.



git log --pretty=format:"%h -- %an" gives just the short commit hash and the author name.



git commit --amend -------------------------------> is used to edit (amend) the most recent commit. It lets you modify the commit message and/or add more changes to the last commit, instead of creating a brand-new commit. It will open editor with the last commit message. You can edit it, save, and close → the commit message gets updated.If you forgot to include some files, just stage them first:

git add <file>

git commit --amend

Now Git will include those staged changes into the previous commit instead of making a new one.





git config --global alias.st status --------------→ Makes git st a shortcut for git status. After running this, instead of typing:

git status

You can simply type:

git st

And it will do the exact same thing.



















git stash ------------------------------------> save your uncommitted changes without committing them. It Takes your modified tracked files (both staged and unstaged). Saves them in a stack-like storage (the stash). Cleans working directory → so you can switch branches or pull updates safely. Later, you can reapply those changes.



🔹 Basic workflow

1\. Save changes

git stash  ----------------------------------------------->  Your working directory goes clean, but changes are saved in stash.



2\. List stashes

git stash list



Example:

stash@{0}: WIP on main: 5d9c1f2 Updated login API

stash@{1}: WIP on feature: c3f8a9d Added tests



3\. Apply stash back

git stash apply stash@{0}   -----------------------------------------------> Reapplies the changes, but keeps the stash in the list.



4\. Apply and remove (pop)

git stash pop  -----------------------------------------------> Reapplies the latest stash and deletes it from the stash list.



5\. Drop stash

git stash drop stash@{0}  -----------------------------------------------> Deletes a specific stash entry.



6\. Clear all stashes

git stash clear  ----------------------------------------------->  Deletes all stashed changes.



🔹 Variants



Save with a message:



git stash push -m "Fixing bug in login API"





Stash including untracked files:



git stash -u





Stash including ignored files:



git stash -a



🔹 Example scenario



You’re on main branch working on app.py.



Suddenly, you need to switch to another branch to fix a bug.



Instead of committing half-done work:



git stash

git checkout hotfix





After fixing bug, come back:



git checkout main

git stash pop





✅ Your half-done work is back, exactly as it was.



🔹 Summary



git stash = temporarily saves your work-in-progress (like a clipboard).



Keeps repo clean for switching branches / pulling code.



You can later restore (pop/apply) or discard (drop) the stash.









We can search based on given pattern in commit message.

git log --grep="pattern" ------------------------------------------------->    It shows all commits which has given pattern in the commit message.

