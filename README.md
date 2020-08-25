# Github-operation-process-lazy-package



## Linux安裝(Linux Installation)

### 「Debian系列安裝(Series Installation)」

或其延伸發行版，如Deepin、Knoppix、Ubuntu

```
$ apt-get install git
```
### 「Red Hat系列安裝(Series Installation)」

或其延伸發行版，如aLinux、CentOS、Fedora、openSUSE

```
$ yum install git-core
```
其他以打包方式套件管理的，如ArchLinux、Gentoo自己想辦法

### 「檢查版本(Check version)」

```
$ git --version
```



## 懶人初次上傳流程(Lazy Upload SOP)
### #0 建立並初始化為目錄(Create and initialize the directory)

cd到你要的專案目錄，一切從這裡開始。首先，先建立一個 README.md檔案，這不是必要但務必養成的好習慣。
```
$ echo "# Practicing Git" > README.md
```



### #1 建立並初始化為目錄(Create and initialize the directory)

建立並初始化為Git目錄，目錄會多出 .git 隱藏資料夾
```
$ git init
```



### #2 設置姓名與郵件(Set name and email)

不曉得甚麼時候開始，這個沒打會錯誤
```
$ git config --global user.name "<Your Name>"
```
```
$ git config --global user.email "<your@gmail.com>"
```



### #3 加入追蹤(Join tracking)

git add .代表加入該目錄所有檔案(有包含子目錄)，你也可以指定部分檔案，如git add hello.html。
```
$ git add .
```



### #4 設置推送標記(Set push tag)

```
$ git commit -m "first commit"
```



### #5 加入遠端練節目錄(Join the remote practice section directory)

```
$ git remote add origin <庫的網址>
```



### #6 推送至遠端(Push to remote)

```
$ git push -u origin master
```



## 更新上傳流程(Update Upload SOP)



## Git常用指令(Git common commands)

| 指令       | 功能                    | 範例       |
| ---------- | ----------------------- | ---------- |
| git init   | 建立並初始化為Git目錄  | git init   |
| git config | 設定或檢視Git設定檔資訊 | git config |
| git add    | 將檔案加入Git暫存區     | git add .  |
| git rm     | 將檔案移除Git暫存區   | git rm hello.kt |
| git mv     | 修改檔名、搬移目錄   | git mv <現在檔名> <改後檔名> |
| git status | 查看Git狀況 | git status |
| git remote | 指定遠端網址     | git remote add origin <網址>   |
| git push    | 推送   | git push -u origin master |
| git pull | 從遠端拉回再合併更新(= git fetch + git merge) | git pull -p |
| git clone | 複製副至本機目錄 | git clone <庫的網址> |
| git log | 顯示過去的版本異動 | git log |
| git reflog | 承上 只是比較詳細 | git reflog |
| git show | 顯示指定的版本異動 | git show HEAD^ |



## 指令詳細用法(Detailed usage of instructions)

- 以下整理自[Tsung's Blog](https://blog.longwin.com.tw/) - Git 初學筆記 - 指令操作教學
- 以及[為你自己學 Git](https://gitbook.tw/)



### 新增檔案(git add)

- git add . # 將資料先暫存到 staging area, add 之後再新增的資料, 於此次 commit 不會含在裡面

- git add <指定檔名>

- git add modify-file # 修改過的檔案, 也要 add. (不然 commit 要加上 -a 的參數)

- git add -u # 只加修改過的檔案, 新增的檔案不加入

- git add -i # 進入互動模式

  
### 標記推送(git Commit)

- git commit

- git commit -m 'commit message'

- git commit -a -m 'commit -message' # 將所有修改過得檔案都 commit, 但是 新增的檔案 還是得要先 add

- git commit -a -v # -v 可以看到檔案哪些內容有被更改, -a 把所有修改的檔案都 commit

  
### 遠端檔案操作(git remote)

- git remote

- git remote add new-branch http://git.example.com.tw/project.git #增加遠端 Repository 的 branch(origin -> project)

- git remote show # 秀出現在有多少 Repository

- git remote rm new-branch # 刪掉

- git remote update # 更新所有 Repository branch

- git branch -r # 列出所有 Repository branch

  


### 產生分支(git branch)
- git branch # 列出目前有多少 branch

- git branch new-branch # 產生新的 branch (名稱: new-branch), 若沒有特別指定, 會由目前所在的 - branch / master 直接複製一份

- git branch new-branch master # 由 master 產生新的 branch(new-branch)

- git branch new-branch v1 # 由 tag(v1) 產生新的 branch(new-branch)

- git branch -d new-branch # 刪除 new-branch

- git branch -D new-branch # 強制刪除 new-branch

- git checkout -b new-branch test # 產生新的 branch，並同時切換過去 new-branch # 與 remote repository 有關

- git branch -r # 列出所有 Repository branch

- git branch -a # 列出所有 branch

  
### 比較檔案(git diff)
- git diff master # 與 Master 有哪些資料不同

- git diff --cached # 比較 staging area 跟本來的 Repository

- git diff tag1 tag2 # tag1，與 tag2 的 diff

- git diff tag1:file1 tag2:file2 # tag1，與 tag2 的 file1, file2 的 diff

- git diff # 比較 目前位置 與 staging area

- git diff --cached # 比較 staging area 與 Repository 差異

- git diff HEAD # 比較目前位置 與 Repository 差別

- git diff new-branch # 比較目前位置 與 branch(new-branch) 的差別

- git diff --stat

  
### 檢查版本異動(git log)
- git log # 將所有 log 秀出

- git log --all # 秀出所有的 log (含 branch)

- git log -p # 將所有 log 和修改過得檔案內容列出

- git log -p filename # 將此檔案的 commit log 和 修改檔案內容差異部份列出

- git log --name-only # 列出此次 log 有哪些檔案被修改

- git log --stat --summary # 查每個版本間的更動檔案和行數

- git log filename # 這個檔案的所有 log

- git log directory # 這個目錄的所有 log

- git log -S'foo()' # log 裡面有 foo() 這字串的.

- git log --no-merges # 不要秀出 merge 的 log

- git log --since="2 weeks ago" # 最後這 2週的 log

- git log --pretty=oneline # 秀 log 的方式

- git log --pretty=short # 秀 log 的方式

- git log --pretty=format:'%h was %an, %ar, message: %s'

- git log --pretty=format:'%h : %s' --graph # 會有簡單的文字圖形化, 分支等

- git log --pretty=format:'%h : %s' --topo-order --graph # 依照主分支排序

- git log --pretty=format:'%h : %s' --date-order --graph # 依照時間排序

  

### 查看資料(git show)

- git show ebff # 查log是commit ebff810c461ad1924fc422fd1d01db23d858773b的內容

- git show v1 # 查 tag:v1 的修改內容

- git show v1:test.txt # 查 tag:v1 的 test.txt 檔案修改內容

- git show HEAD # 此版本修改的資料

- git show HEAD^ # 前一版修改的資料

- git show HEAD^^ # 前前一版修改的資料

- git show HEAD~4 # 前前前前一版修改的資料

  

### 還原(git reset)

- git reset --hard HEAD # 還原到最前面

- git reset --hard HEAD~3

- git reset --soft HEAD~3

- git reset HEAD filename # 從 staging area 狀態回到 unstaging 或 untracked (檔案內容並不會改變)

  

### 注意事項(Precautions)
project/.git/config 



## 參考(Reference)

以上內容整理自多處網站、書籍、朋友經驗及個人經驗

https://gitbook.tw/

[https://blog.longwin.com.tw/2009/05/git-learn-initial-command-2009/](https://blog.longwin.com.tw/2009/05/git-learn-initial-command-2009/)