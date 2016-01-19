# githug-
githug通关笔记
#githug通关大冒险&史上最全攻略

### 安装githug
sudo gem install githug 

在这个选项中，选择y

No githug directory found, do you wish to create one? [yn]  y

## Question #1

Name: init
Level: 1
Difficulty: *

A new directory, `git_hug`, has been created; initialize an empty repository in it.

## Answer #1
cd git_hug
git init


## Question #2
Name: config
Level: 2
Difficulty: *

Set up your git name and email, this is important so that your commits can be identified.

## Answer #2
git config -l 查看所有设置

git config --unset-all user.name

git config —-add —global user.name ZZZ

git config —-add —global user.email XXX@YYY

注解：

--global              use global config file  ~/.gitconfig (or ~/.config/git/config

--system              use system config file  /etc/gitconfig

--local               use repository config file

请记住name和email，稍后会验证你刚才创建的名字和邮箱

## Question #3
Name: add
Level: 3
Difficulty: *

There is a file in your folder called `README`, you should add it to your staging area
Note: You start each level with a new repo. Don't look for files from the previous one.

## Answer #3
 git add README


## Question #4
Name: commit
Level: 4
Difficulty: *

The `README` file has been added to your staging area, now commit it.

## Answer #4
git commit -m "init"


## Question #5
Name: clone
Level: 5
Difficulty: *
Clone the repository at https://github.com/Gazler/cloneme.

## Answer #5
git clone https://github.com/Gazler/cloneme


## Question #6
Name: clone_to_folder
Level: 6
Difficulty: *

Clone the repository at https://github.com/Gazler/cloneme to `my_cloned_repo`.

## Answer #6
git clone https://github.com/Gazler/cloneme my_cloned_repo

## Question #7
Name: ignore
Level: 7
Difficulty: **

The text editor 'vim' creates files ending in `.swp` (swap files) for all files that are currently open.  We don't want them creeping into the repository.  Make this repository ignore `.swp` files.

## Answer #7
vi .gitignore
添加 ＊.swp


## Question #8
Name: include
Level: 8
Difficulty: **

Notice a few files with the '.a' extension.  We want git to ignore all but the 'lib.a' file.
vi .gitignore

## Answer #8
添加*.a !lib.a 注意字符问题


## Question #9
Name: status
Level: 9
Difficulty: *

There are some files in this repository, one of the files is untracked, which file is it?

## Answer #9
git status
database.yml


## Question #10
Name: number_of_files_committed
Level: 10
Difficulty: *

There are some files in this repository, how many of the files will be committed?

## Answer #10
git status 
2

## Question #11
Name: rm
Level: 11
Difficulty: **

A file has been removed from the working tree, however the file was not removed from the repository.  Find out what this file was and remove it.

## Answer #11
git rm deleteme.rb

git rm命令把一个文件删除，并把它从git的仓库管理系统中移除。但是注意最后要执行git commit才真正提交到git仓库


## Question #12
Name: rm_cached
Level: 12
Difficulty: **

A file has accidentally been added to your staging area, find out which file and remove it from the staging area.  *NOTE* Do not remove the file from the file system, only from git.
git rm --cached <file>..." to unstage

## Answer #12
git rm --cached deleteme.rb


## Question #13
Name: stash
Level: 13
Difficulty: **

You've made some changes and want to work on them later. You should save them, but don't commit them.

## Answer #13
git stash

当前工作区内容已被修改，但是并未完成。这时Boss来了，说前面的分支上面有一个Bug，需要立即修复。可是我又不想提交目前的修改，因为修改没有完成。但是，不提交的话，又没有办法checkout到前面的分支。此时用Git Stash就相当于备份工作区了。然后在Checkout过去修改，就能够达到保存当前工作区，并及时恢复的作用。
Use git stash when you want to record the current state of the working directory and the index, but want to go back to a clean working directory. The command saves your local modifications away and reverts the working directory to match the HEAD commit.
相当于保存当时暂存区和工作目录，想回到纯净的工作目录。


## Question #14
Name: rename
Level: 14
Difficulty: ***

We have a file called `oldfile.txt`. We want to rename it to `newfile.txt` and stage this change.

## Answer #14
git mv oldfile.txt newfile.txt
git add newfile.txt


## Question #15
Name: restructure
Level: 15
Difficulty: ***

You added some files to your repository, but now realize that your project needs to be restructured.  Make a new folder named `src` and using Git move all of the .html files into this folder.

## Answer #15
mkdir src
git mv *.html src

## Question #16
Name: log
Level: 16
Difficulty: **

You will be asked for the hash of most recent commit.  You will need to investigate the logs of the repository for this.

## Answer #16
git log
af37a6cea9a328fa49b37f36369ddb15a9d9abae


## Question #17
Name: tag
Level: 17
Difficulty: **

We have a git repo and we want to tag the current commit with `new_tag`.

## Answer #17
 git tag new_tag


## Question #18
Name: push_tags
Level: 18
Difficulty: **

There are tags in the repository that aren't pushed into remote repository. Push them now.

From /var/folders/gy/wj4_q1ss0sxd826lt10dy0ww0000gn/T/d20160119-1699-196dy5q/
 * [new branch]      master     -> origin/master

## Answer #18
 git push origin --tags


## Question #19
Name: commit_amend
Level: 19
Difficulty: **

The `README` file has been committed, but it looks like the file `forgotten_file.rb` was missing from the commit.  Add the file and amend your previous commit to include it.

## Answer #19
git add forgotten_file.rb
git commit --amend


## Question #20
Name: commit_in_future
Level: 20
Difficulty: **

Commit your changes with the future date (e.g. tomorrow).

## Answer #20
git commit --date="Wed Feb 16 14:00 2037 +0100"

## Question #21
Name: reset
Level: 21
Difficulty: **

There are two files to be committed.  The goal was to add each file as a separate commit, however both were added by accident.  Unstage the file `to_commit_second.rb` using the reset command (don't commit anything).

## Answer #21
git reset HEAD to_commit_second.rb
撤销提交到暂存区的东东，重置到HEAD指针


## Question #22
Name: reset_soft
Level: 22
Difficulty: **

You committed too soon. Now you want to undo the last commit, while keeping the index.

## Answer #22
git reset --soft HEAD^1
—-soft —hard —-mixed


## Question #23
Name: checkout_file
Level: 23
Difficulty: ***

A file has been modified, but you don't want to keep the modification.  Checkout the `config.rb` file from the last commit.

## Answer #23
git checkout -- config.rb


## Question #24
Name: remote
Level: 24
Difficulty: **

This project has a remote repository.  Identify it.

## Answer #24
git remote -v
my_remote_repo


## Question #25
Name: remote_url
Level: 25
Difficulty: **

The remote repositories have a url associated to them.  Please enter the url of remote_location.

## Answer #25
git remote -v

https://github.com/githug/not_a_repo


## Question #26
Name: pull
Level: 26
Difficulty: **

You need to pull changes from your origin repository.

## Answer #26
git pull origin mater


## Question #27
Name: remote_add
Level: 27
Difficulty: **

Add a remote repository called `origin` with the url https://github.com/githug/githug

## Answer #27
git remote add origin https://github.com/githug/githug

## Question #28
Name: push
Level: 28
Difficulty: ***

Your local master branch has diverged from the remote origin/master branch. Rebase your commit onto origin/master and push it to remote.

remote: Counting objects: 2, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 2 (delta 0), reused 0 (delta 0)
Unpacking objects: 100% (2/2), done.
From /var/folders/gy/wj4_q1ss0sxd826lt10dy0ww0000gn/T/d20160119-2030-1j5obov/
 * [new branch]      master     -> origin/master

## Answer #28
git rebase origin/master
git push origin master


## Question #29
Name: diff
Level: 29
Difficulty: **

There have been modifications to the `app.rb` file since your last commit.  Find out which line has changed.

## Answer #29
 git diff app.rb

26

## Question #30
Name: blame
Level: 30
Difficulty: **

Someone has put a password inside the file `config.rb` find out who it was.

## Answer #30
git blame config.rb


## Question #31
Name: branch
Level: 31
Difficulty: *

You want to work on a piece of code that has the potential to break things, create the branch test_code.

## Answer #31
git branch test_code


## Question #32
Name: checkout
Level: 32
Difficulty: **

Create and switch to a new branch called my_branch.  You will need to create a branch like you did in the previous level.

## Answer #32
git checkout -b my_branch


## Question #33
Name: checkout_tag
Level: 33
Difficulty: **

You need to fix a bug in the version 1.2 of your app. Checkout the tag `v1.2`.

## Answer #33
git checkout -b v1.2


## Question #34
Name: checkout_tag_over_branch
Level: 34
Difficulty: **

You need to fix a bug in the version 1.2 of your app. Checkout the tag `v1.2` (Note: There is also a branch named `v1.2`).

## Answer #34
git checkout -b tags/v1.2


## Question #35
Name: branch_at
Level: 35
Difficulty: ***

You forgot to branch at the previous commit and made a commit on top of it. Create branch test_branch at the commit before the last.

## Answer #35
git branch test_branch HEAD^1


## Question #36
Name: delete_branch
Level: 36
Difficulty: **

You have created too many branches for your project. There is an old branch in your repo called 'delete_me', you should delete it.

## Answer #36
git branch -d delete_me


## Question #37
Name: push_branch
Level: 37
Difficulty: **

You've made some changes to a local branch and want to share it, but aren't yet ready to merge it with the 'master' branch.  Push only 'test_branch' to the remote repository

## Answer #37
git push origin test_branch


## Question #38
Name: merge
Level: 38
Difficulty: **

We have a file in the branch 'feature'; Let's merge it to the master branch.

## Answer #38
git merge feature


## Question #39
Name: fetch
Level: 39
Difficulty: **

Looks like a new branch was pushed into our remote repository. Get the changes without merging them with the local repository

## Answer #39
git fetch origin


## Question #40
Name: rebase
Level: 40
Difficulty: **

We are using a git rebase workflow and the feature branch is ready to go into master. Let's rebase the feature branch onto our master branch.

## Answer #40
git checkout feature
git rebase master


## Question #41
Name: repack
Level: 41
Difficulty: **

Optimise how your repository is packaged ensuring that redundant packs are removed.


## Answer #41
git gc [这个需要搞明白]


## Question #42
Name: cherry-pick
Level: 42
Difficulty: ***

Your new feature isn't worth the time and you're going to delete it. But it has one commit that fills in `README` file, and you want this commit to be on the master as well.

## Answer #42
需要先查看对应提交的hash。
git checkout new-feature
git log
git cherry-pick  ca32a6dac7b6f97975edbe19a4296c2ee7682f68


## Question #43
Name: grep
Level: 43
Difficulty: **

Your project's deadline approaches, you should evaluate how many TODOs are left in your code

## Answer #43
git grep ‘TODO' 4
git grep 'TODO' | wc -l


## Question #44
Name: rename_commit
Level: 44
Difficulty: ***

Correct the typo in the message of your first (non-root) commit.

## Answer #44
git rebase -i HEAD~2
将first commit 的编辑选项改完r  就可以改名字。删除多余的m


## Question #45
Name: squash
Level: 45
Difficulty: ****

You have committed several times but would like all those changes to be one commit.


## Answer #45
git rebase -i HEAD~4
将后三个的命令统统改为s



## Question #46
Name: merge_squash
Level: 46
Difficulty: ***

Merge all commits from the long-feature-branch as a single commit.

## Answer #46
git merge --squash long-feature-branch
git commit -m "XXX"


## Question #47
Name: reorder
Level: 47
Difficulty: ****

You have committed several times but in the wrong order. Please reorder your commits.

## Answer #47
git rebase -i HEAD~3
颠倒下顺序。


## Question #48
Name: bisect
Level: 48
Difficulty: ***

A bug was introduced somewhere along the way.  You know that running `ruby prog.rb 5` should output 15.  You can also run `make test`.  What are the first 7 chars of the hash of the commit that introduced the bug.


## Answer #48
git bisect start
git bisect good f608824
git bisect master

每次都运行make test 运行成功 git bisect good 运行失败 git bisect bad

18ed2ac

 或者直接运行 git bisect run make test

## Question #49
Name: stage_lines
Level: 49
Difficulty: ****

You've made changes within a single file that belong to two different features, but neither of the changes are yet staged. Stage only the changes belonging to the first feature.


## Answer #49
git add feature.rb -e
进入到编辑模式，将第二个提交删掉


## Question #50
Name: find_old_branch
Level: 50
Difficulty: ****

You have been working on a branch but got distracted by a major issue and forgot the name of it. Switch back to that branch.


## Answer #50
git reflog

894a16d HEAD@{0}: commit: commit another todo
6876e5b HEAD@{1}: checkout: moving from solve_world_hunger to kill_the_batman
324336a HEAD@{2}: commit: commit todo
6876e5b HEAD@{3}: checkout: moving from blowup_sun_for_ransom to solve_world_hunger
6876e5b HEAD@{4}: checkout: moving from kill_the_batman to blowup_sun_for_ransom
6876e5b HEAD@{5}: checkout: moving from cure_common_cold to kill_the_batman
6876e5b HEAD@{6}: commit (initial): initial commit

solve_world_hunger



## Question #51
Name: revert
Level: 51
Difficulty: ****

You have committed several times but want to undo the middle commit.
All commits have been pushed, so you can't change existing history.

## Answer #51
git revert ba649f24864329840bc97fe6117e69600c0fd8b2

## Question #52
Name: restore
Level: 52
Difficulty: ****

You decided to delete your latest commit by running `git reset --hard HEAD^`.  (Not a smart thing to do.)  You then change your mind, and want that commit back.  Restore the deleted commit.

## Answer #52
git reflog 比较详细的列出ref的变更历史
git cherry-pick


## Question #53
Name: conflict
Level: 53
Difficulty: ****

You need to merge mybranch into the current branch (master). But there may be some incorrect changes in mybranch which may cause conflicts. Solve any merge-conflicts you come across and finish the merge.


## Answer #53
git merge mybranch
 vi poem.txt 去除冲突部分
git add poem.txt

 git commit -m "deal with conflict"


## Question #54
Name: submodule
Level: 54
Difficulty: **

You want to include the files from the following repo: `https://github.com/jackmaney/githug-include-me` into a the folder `./githug-include-me`. Do this without cloning the repo or copying the files from the repo into this repo.


## Answer #54
 git submodule add https://github.com/jackmaney/githug-include-me ./githug-include-me


## Question #55
Name: contribute
Level: 55
Difficulty: ***

This is the final level, the goal is to contribute to this repository by making a pull request on GitHub.  Please note that this level is designed to encourage you to add a valid contribution to Githug, not testing your ability to create a pull request.  Contributions that are likely to be accepted are levels, bug fixes and improved documentation.

最后一个就看大家自己喽～～
