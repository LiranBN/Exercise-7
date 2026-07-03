# Exercise-7
 Git exercises
in any block that have question will be sections with answers at it the end of the block
 
## Block 1 – First Local Repository: Core Workflow
no issues was found at this block
## Block 2 – Changing & Undoing Safely
### 2. Check the status and review the changes.
GIT status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   ex7.py
### 3. Stage and commit the updated file.
git add ex7.py
git commit -m "update : update the file by insert pront command"
[main 23ab1b0] update : update the file by insert pront command
 1 file changed, 1 insertion(+)

### 5. Explore how to compare this broken version with the committed version.
git diff 23ab1b0
diff --git a/ex7.py b/ex7.py
index 7849600..93e8835 100644
--- a/ex7.py
+++ b/ex7.py
@@ -1 +1,2 @@
-print("liran created this file")
\ No newline at end of file
+print("liran created this file")
+pirnt
\ No newline at end of file

### 6.Restore the file to the last committed version.
git restore ex7.py 

### 7. Make another commit, then practice undoing that commit using a safe method.
git add ex7.py

git commit -m "add  a new line"
[main 844983e] add  a new line
 1 file changed, 2 insertions(+), 1 deletion(-)

 git revert HEAD

## Block 3 – Branching & Merging
### 1. Create a new branch called experiment-linear.
git branch experiment-linear
git switch experiment-linear
M       ex7.py
Switched to branch 'experiment-linear'

### 3. Commit the change.
git add ex7.py                   
git commit -m " change the file for block 3.2"
[experiment-linear 7669b4d]  change the file for block 3.2
 1 file changed, 3 insertions(+), 1 deletion(-)

### 4. Switch back to the main branch.
git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

### 6. Switch back to your experimental branch and confirm the change is still there.
git switch experiment-linear
Switched to branch 'experiment-linear'

### 7. Merge the experimental branch into main.
git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

git merge experiment-linear
Updating 844983e..7669b4d
Fast-forward
 ex7.py | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)

### answers
#### 1. the changes disappeared on main, because the changes where committed on experiment-linear and not on main
#### 2. the branches solved a problem that to teams can work on deferent things without interfere  each other 
#### 3. there are several reason for it :
1. the main version will always be the stable branch of the production.
2. server programmer can work on the same project without with out interfere  each other.
3.  reduce the risk of bug - if you create changes with bug it will be isolated from the main until you solve it . 


## Block 4 – Working With Remotes (GitHub)
done without any issues

## Block 5 – Fetch vs Pull
### 1. PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7> git add ex7.py
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7> git commit -m "changes for 5.1"
[main d5eb79b] changes for 5.1
 1 file changed, 3 insertions(+), 1 deletion(-)
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7> git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 356 bytes | 356.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/LiranBN/Exercise-7
   7669b4d..d5eb79b  main -> main

### 2. In the second copy, check for updates without modifying your files.
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git fetch
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 3 (delta 1), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 336 bytes | 12.00 KiB/s, done.
From https://github.com/LiranBN/Exercise-7
   7669b4d..d5eb79b  main       -> origin/main
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean

### 4. Bring the update into your working copy.
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git merge
Updating 7669b4d..d5eb79b
Fast-forward
 ex7.py | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)

### 5.Review the difference between “fetch” and “pull”.
fetch only bring the changes but do not change the files. to actually change the files the user need to do merge after the fetch . pull is bringing the changes and update the files with them.

## Block 6 – Merge Conflict Practice
### 1. In copy A, create a new file and commit it.
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7> git add new-file.py                            
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7> git commit new-file.py -m "add new file at copy A"
[main a89b699] add new file at copy A
 1 file changed, 1 insertion(+)
 create mode 100644 new-file.py

### 2. Push the commit to GitHub.
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7> git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 360 bytes | 180.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/LiranBN/Exercise-7
   d5eb79b..a89b699  main -> main

### 4. Commit the change and attempt to push.
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git add new-file.py
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git commit -m "add new file at copy B"
[main 51380c7] add new file at copy B
 1 file changed, 1 insertion(+)
 create mode 100644 new-file.py
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git push
To https://github.com/LiranBN/Exercise-7
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/LiranBN/Exercise-7'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

### 6. Pull the remote changes to trigger a conflict.

git pull
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 340 bytes | 14.00 KiB/s, done.
From https://github.com/LiranBN/Exercise-7
   d5eb79b..a89b699  main       -> origin/main
Auto-merging new-file.py
CONFLICT (add/add): Merge conflict in new-file.py
Automatic merge failed; fix conflicts and then commit the result.

## 8. Stage, commit, and push the resolved version.
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git add new-file.py
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git commit -m "resolve the versions"
[main b28f6a0] resolve the versions
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\new clone\Exercise-7> git push
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 619 bytes | 619.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/LiranBN/Exercise-7
   a89b699..b28f6a0  main -> main

##  Block 7 – AI-Focused Exercise: Config Versioning & Experiment Tracking
### 1. Create a new project for ML experiments.
md ML-Experiments


    Directory: C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7


Mode                 LastWriteTime         Length Name                                                              
----                 -------------         ------ ----                                                              
d-----          7/3/2026   4:45 PM                ML-Experiments                

git add .

git commit -m "Create ML experiments project"
On branch main
Your branch is up to date with 'origin/main'.

### 3. Commit the baseline configuration.
git add config.json
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7\ML-Experiments> git commit -m "Add model configuration file"

[main 4973e27] Add model configuration file
 1 file changed, 12 insertions(+)
 create mode 100644 ML-Experiments/config.json

### 4. Create a new branch for an experiment.

git branch ML-experiments
PS C:\Users\barne\OneDrive\מסמכים\AI-Exercise\Exercise-7\ML-Experiments> git switch ML-experiments
Switched to branch 'ML-experiments'

### 6. Commit the experiment configuration.
git add config.json    

git commit -m "changed the config parameters"
[ML-experiments f102f2a] changed the config parameters
 1 file changed, 1 insertion(+), 1 deletion(-)

### 7.  Tag the experiment’s commit to mark it as a “best model version”.
git tag best-model-v1

### 8. Switch back to the main branch.
 git switch main

## Block 8 – Confidence Checklist
Check off the Git concepts you feel comfortable with:

 - [x] Initializing repositories
 - [x] Tracking and committing changes
 - [x] Viewing history
 - [x] Inspecting modifications
 - [x] Undoing changes safely
 - [x] Using branches
 - [x] Merging branches
 - [x] Connecting to remotes
 - [x] Pushing and pulling
 - [x] Resolving merge conflicts
 - [x] Using tags for experiment tracking
