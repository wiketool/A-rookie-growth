# 养成之Git特别篇

[^简介]:这篇学习笔记记录了一个菜鸟的成长过程



## 安装

1. 从Git官网下载Git并安装

2. 在CMD中输入

   ```bash
   git --version
   ```

   以检查Git已经正确配置环境变量

3. 在右键菜单中打开Git Bash

## 使用

### 从本地创建仓库

1. 找到项目所在的文件夹

2. ```bash
   git init	//初始化Git仓库
   ```

3. ```bash
   git add *.c   //将.c后后缀的文件添加到暂存区
   git add LICENSE		//将LICENSE添加到暂存区
   git commit -m 'initial project version'
   ```

4. 创建README文件

   ```bash
   git status
   ```

   ```bash
   On branch master
   Untracked files:
     (use "git add <file>..." to include in what will be committed)
           README
   
   nothing added to commit but untracked files present (use "git add" to track)
   
   ```

   新创建的文件Git不会将其自动列入追踪的文件当中

5. ```bash
   git add README
   git status
   ```

   ```bash
   On branch master
   Changes to be committed:
     (use "git restore --staged <file>..." to unstage)
           new file:   README
   ```

6. 修改README文件

   ```bash
   git status
   ```

   ```bash
   On branch master
   Changes to be committed:
     (use "git restore --staged <file>..." to unstage)
           new file:   README
   
   Changes not staged for commit:
     (use "git add <file>..." to update what will be committed)
     (use "git restore <file>..." to discard changes in working directory)
           modified:   README
   ```

   > 说明已跟踪文件的内容发生了变化，但还没有放到暂存区。 要暂存这次更新，需要运行 git add 命令。可以用它开始跟踪新文件，或者把已跟踪的文件放到暂存区，还能用于合并时把有冲突的文件标记为已解决状态等。

   可以将 git add 理解为‘精确地将内容添加到下一次更改中’。

7. ```bash
   git status -s
   git status --short
   ```

   以更简洁的方式查看文件状态

8. ```bash
   cat .gitignore
   ```

   ```bash
   # 忽略所有的 .a 文件
   *.a
   # 但跟踪所有的 lib.a，即便你在前面忽略了 .a 文件
   !lib.a
   # 只忽略当前目录下的 TODO 文件，而不忽略 subdir/TODO
   /TODO
   # 忽略任何目录下名为 build 的文件夹
   build/
   # 忽略 doc/notes.txt，但不忽略 doc/server/arch.txt
   doc/*.txt
   # 忽略 doc/ 目录及其所有子目录下的 .pdf 文件
   doc/**/*.pdf
   ```

9. ```bash
   git diff
   ```

   > 此命令比较的是工作目录中当前文件和暂存区域快照之间的差异

   

   ```bash
   git diff --staged
   ```

   > 这条命令将比对已暂存文件与最后一次提交的文件差异

   

10. 也可以在 commit 命令后添加 -m 选项，将提交信息与命令放在同一行，如下所示：

    ```bash
    git commit -m "Story 182: Fix benchmarks for speed"
    ```

11. 从工作目录中删除某文件

    ```bash
    git rm *
    ```

    >  如果要删除之前修改过或已经放到暂存区的文件，则必须使用 强制删除选项 -f（译注：即 force 的首字母）。 这是一种安全特性，用于防止误删尚未添加到快照的数据，这 样的数据不能被 Git 恢复。

    想要从暂存区删除某文件时

    ```bash
    git rm --cached *
    ```

12. 撤销上一次提交

    情景演示(本应提交a.txt和b.txt)

    ```bash
    git add a.txt
    git commit -m 'Forget'
    ```

    现在很后悔，于是发挥超能力

    ```bash
    git add b.txt
    git commit --amend
    ```

13. 