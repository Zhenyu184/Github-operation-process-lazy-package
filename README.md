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
執行`git init`:
```
$ git init
```
```
$ git config --global user.name "<Your Name>"
```
```
$ git config --global user.email "<your@gmail.com>"
```



## 更新上傳流程(Update Upload SOP)



## Git常用指令(Git common commands)

| 指令       | 功能                    | 範例       |
| ---------- | ----------------------- | ---------- |
| git init   | 建立並初始化為Git目錄  | git init   |
| git config | 設定或檢視Git設定檔資訊 | git config |
| git add    | 將檔案加入Git暫存區     | git add .  |
| git rm     | 將檔案移除Git暫存區   | git rm hello.kt |
| git status | 查看Git狀況 | git status |
| git remote | 指定遠端網址     | git remote add origin <網址>   |
| git push    | 推送   | git push -u origin master |
| git pull | 從遠端拉回再合併更新(= git fetch + git merge) | git pull -p |
| git clone | 複製副至本機目錄 | git clone <庫的網址> |
| git log | 顯示過去的版本異動 | git log |

