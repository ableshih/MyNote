# GIT

---

## 指令

---

### add
### commit
### checkout 
### log
### rm
### mv
### diff 
### reset
### dist
### config
### --version
### init
### status
### gitk
### master 
### main 
### branch 
### merge 
### $ git checkout master
### $ git merge one

---

## tokens
1-Settings -> 
2-Developer settings -> 
3-Personal access tokens -> 
4-tokens (classic) -> 
5-Generate new token -> 
6-Generate new token(classic)

1-https://github.com/settings/profile
2-https://github.com/settings/apps
4-https://github.com/settings/tokens
6-https://github.com/settings/tokens/new


---

## 情境
```
1. 開啟新的分支： $ git branch <branchName>
2. 確認目前所在分支： $ git branch -v
3. 切換分支： $ git checkout <branchName>
4. 刪除分支： $ git branch -r <branchName>
5. 合併分支： $ git merge <被合併分支 branchName>

假設在合併時發生衝突，必須開啟檔案手動解決衝突，重新 $ git add 並 $ git commit ，git 會新增一個版本。
```
---

## 官網範例

### create a new repository on the command line
```
echo "# yyuu" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/ableshih/yyuu.git
git push -u origin main
```
### push an existing repository from the command line
```
git remote add origin https://github.com/ableshih/yyuu.git
git branch -M main
git push -u origin main
```   
    
### create a new repository on the command line
```
echo "# yyuu" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:ableshih/yyuu.git
git push -u origin main
```
### push an existing repository from the command line
```
git remote add origin git@github.com:ableshih/yyuu.git
git branch -M main
git push -u origin main
```
---

### help
```
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--super-prefix=<path>] [--config-env=<name>=<envvar>]
           <command> [<args>]
```
---
```
These are common Git commands used in various situations:
```
### start a working area (see also: git help tutorial)
#### clone
Clone a repository into a new directory
#### init
Create an empty Git repository or reinitialize an existing one

### work on the current change (see also: git help everyday)
#### add
Add file contents to the index
#### mv
Move or rename a file, a directory, or a symlink
#### restore
Restore working tree files
#### rm
Remove files from the working tree and from the index

### examine the history and state (see also: git help revisions)
#### bisect
Use binary search to find the commit that introduced a bug
#### diff
Show changes between commits, commit and working tree, etc
#### grep
Print lines matching a pattern
#### log
Show commit logs
#### show
Show various types of objects
#### status
Show the working tree status

### grow, mark and tweak your common history
#### branch
List, create, or delete branches
#### commit
Record changes to the repository
#### merge
Join two or more development histories together
#### rebase
Reapply commits on top of another base tip
#### reset
Reset current HEAD to the specified state
#### switch
Switch branches
#### tag
Create, list, delete or verify a tag object signed with GPG

### collaborate (see also: git help workflows)
#### fetch
Download objects and refs from another repository
#### pull
Fetch from and integrate with another repository or a local branch
#### push
Update remote refs along with associated objects

### help
'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
See 'git help git' for an overview of the system.



```
Git版本控制
使用數據庫管理歷史記錄
記錄修改的提交
工作目錄與索引
教學1 開始使用Git
安裝Git
初始設定
新建數據庫
提交檔案
共享數據庫
Push到遠端數據庫
複製遠端數據庫
從遠端數據庫執行Pull
教學2 共享數據庫
在貝格樂上建立遠端數據庫
Push到遠端數據庫
複製遠端數據庫
在複製的本地端數據庫執行push
從遠端數據庫執行Pull
合併修改記錄
合併修改記錄
解決衝突
教學3 合併修改記錄
製造衝突
解決衝突
    
    
分支 (branch)
什麼是分支？
分支的運用
分支的切換
分支的合併
Topic分支和integration分支的運用實例
教學1 使用分支
0. 事前準備
1. 建立分支
2. 切換分支
3. 合併分支
4. 刪除分支
5. 平行操作
6. 解決合併的衝突
7. 用rebase合併
遠端數據庫
Pull
Fetch
Push
標籤
標籤
教學2 使用標籤
0. 事前準備
1. 添加輕量標籤
2. 添加標示標籤
3. 刪除標籤
改寫提交
修改最近的提交
取消過去的提交
放棄提交
提取提交
改寫提交的記錄
匯合分支上的提交一同合併
教學3 改寫提交
1. Commit --amend
2. Revert
3. Reset
4. Cherry-pick
5. 使用 rebase -i 合併提交
6. 使用 rebase -i 修改提交
7. Merge --squash
    
基本操作
建立數據庫
註冊檔案或目錄到索引
提交添加到索引的檔案
顯示修改檔案清單
查看修改檔案的差異
顯示提交記錄
查看提交的詳細記錄
修改/移動一個檔案/目錄的名稱
刪除檔案
從工作目錄刪除非管理對象的檔案
還原在工作目錄已更改的檔案
刪除已註冊到索引的檔案
只註冊已提交過的檔案到索引
操作分支
顯示分支清單
建立分支
修改分支的名稱
刪除分支
切換分支
合併分支
操作標籤
顯示標籤清單
建立標籤
建立含註解的標籤
刪除標籤
設定SSH連接
設定SSH連接 (Windows)
設定SSH連接（Mac）
設定SSH連接（主控台）
在貝格樂設定SSH公開金鑰
操作提交記錄
修改最近的提交記錄
只修改最近的提交記錄的註解
修改過去的提交記錄
只修改過去提交記錄的註解
中途停止rebase
查看HEAD的移動記錄
查看分支的移動記錄
刪除最近的提交
放棄rebase
取消最近的reset
複製在另一個分支的提交
查找包含特定註解的提交
    
遠端操作
複製既有的遠端數據庫
添加一個遠端數據庫
顯示遠端數據庫清單
取遠端數據庫的分支建立本地端數據庫的分支
在遠端數據庫建立分支/push修改內容到分支
查看遠端數據庫分支的修改內容
合併遠端數據庫的分支的修改內容
刪除遠端數據庫的分支
建立遠端數據庫的標籤
刪除遠端數據庫的標籤
修改已註冊的遠端數據庫的位址
修改已註冊的遠端數據庫名稱
Git設定
設定用戶名稱/電子郵件
設定輸出顏色
設定命令的別名
不用的檔案歸到非管理對象
將空白目錄設定為管理對象
顯示設定清單
通過代理主機連接HTTP
通過需要用戶認證的代理主機連接HTTP
暫存
暫時儲存現狀的操作
顯示暫存清單
恢復暫存的操作
刪除暫存的操作
刪除所有暫存的操作
Git 和 Subversion的相比
Git和Subversion的命令比較表
疑難排解
SSH
用SSH連接遠端數據庫的時候會顯示”Permission denied (publickey).”
HTTPS
在HTTPS不能clone
HTTPS執行push/pull時每次都需要密碼
SSH/HTTPS共同問題
Push後，無法將變更上傳到遠端數據庫
    
    
建立數據庫
```$ git init```
在要建立數據庫的目錄裡執行init命令。

入門篇 【教學1 Git的基本介紹 】 新建數據庫

Back To Top
註冊檔案或目錄到索引
```$ git add <filepattern>```
在 filepattern 可以直接指定檔案名稱，也可以給予指令例如 "*.txt"的通用字元。如果給予指令 "."的話，可以將子目錄裡的所有檔案註冊到索引裡。

加上 -p 參數，可以選擇只註冊檔案中修改的其中一部分。 加上 -i 參數的話，會以互動方式詢問要註冊在索引裡的檔案。

入門篇 【教學1 Git的基本介紹】 提交檔案

Back To Top
提交添加到索引的檔案
```$ git commit```
添加-a參數，就可以檢測出有修改的檔案(不包括新增的檔案)，將其加入索引並提交。這些操作只要一個指令就可以完成了。
加上-m參數，就可以指令提交“提交訊息”。如果不添加-m參數，就會啟動修改提交訊息的編輯器。

入門篇 【教學1 Git的基本介紹】 提交檔案

Back To Top
顯示修改檔案清單
```$ git status```
加上 -s 參數，僅會顯示已修改的檔案名稱。
如果在 -s 後再加上 -b 參數，則會顯示分支的名稱。

Back To Top
查看修改檔案的差異
```$ git diff```
僅使用 "diff" 命令時，會顯示工作目錄和索引的差異。
加上 --cached 參數，會顯示索引與 HEAD 的差異。
如果指定特定的HEAD 或提交，則可以顯示工作目錄和指定HEAD/提交之間的差異。

Back To Top
顯示提交記錄
```$ git log```
僅使用“log" 將顯示分支的提交列表。
如果要查看特定檔案的提交記錄，請指定檔案名稱。

Back To Top
查看提交的詳細記錄
```$ git show <commit>```
請使用show命令，show命令的參數可以指定log命令參閱的提交與HEAD。

Back To Top
修改/移動一個檔案/目錄的名稱
```$ git mv <oldfilename> <newfilename>```
Back To Top
刪除檔案
```$ git rm <file>```
Back To Top
從工作目錄刪除非管理對象的檔案
```$ git clean```
加上 -n 參數，可以查看將被刪除的檔案。
若添加 -f 參數則會立即刪除檔案。

在預設情況下 .gitignore 檔案中所列之檔案/目錄並不在刪除範圍內。不過如果加上-x 參數， .gitignore 檔案中的檔案/目錄也會從工作目錄中刪除。

Back To Top
還原在工作目錄已更改的檔案
```$ git checkout -- <file>```
Back To Top
刪除已註冊到索引的檔案
```$ git reset HEAD -- <file>```
Back To Top
只註冊已提交過的檔案到索引
```$ git add -u```
Back To Top

操作分支
顯示分支清單
建立分支
修改分支的名稱
刪除分支
切換分支
合併分支
顯示分支清單
```$ git branch```
加上 -r 參數，將顯示遠端分支。
加上 -a 參數，可以顯示遠端與本地端的分支。

Back To Top
建立分支
```$ git branch <branchname>```
進階篇 【教學1 使用分支】 1. 建立分支

Back To Top
修改分支的名稱
```$ git branch -m <oldbranch> <newbranch>```
Back To Top
刪除分支
```$ git branch -d <branchname>```
如果有未合併到 HEAD 的提交，則不能刪除此分支。如果要強制刪除未提交的分支，請加上 -D 參數執行。

進階篇 【教學1 使用分支】 4. 刪除分支

Back To Top
切換分支
```$ git checkout <branch>```
如果添加-b 選項，只需ㄧ個命令就可以執行新建分支和已建分支之間的切換。

進階篇 【分支】 分支的切換
進階篇 【教學1 使用分支】 2. 切換分支

Back To Top
合併分支
```$ git merge <branch>```
加上 --no-ff 參數，將建立合併提交，而不是使用 fast-forward 合併。這可以保留分支合併的紀錄，是個非常有用的參數。

進階篇 【分支】分支的合併
進階篇 【教學1 使用分支】 3. 合併分支

Back To Top

    
操作標籤
顯示標籤清單
建立標籤
建立含註解的標籤
刪除標籤
顯示標籤清單
```$ git tag```
加上 -n 參數，就可以顯示標籤的註解。

Back To Top
建立標籤
```$ git tag <tagname>```
Back To Top
建立含註解的標籤
```$ git tag -a <tagname>```
Back To Top
刪除標籤
```$ git tag -d <tagname>```
Back To Top

    
設定SSH連接
設定SSH連接 (Windows)
設定SSH連接（Mac）
設定SSH連接（主控台）
在貝格樂設定SSH公開金鑰
設定SSH連接 (Windows)
從『開始』界面的『程式集』中開啟『 TortoiseGit 』的項目，啟動Puttygen。

打開TortoiseGit目錄，啟動Puttygen

點擊Generate 按鈕，在進度條進行到最右邊位置以前，請在顯示為紅色框框的範圍內移動滑鼠。

在進度條進行到最右邊位置為前，請在顯示為紅色框框的範圍內移動滑鼠。

金鑰產生後，會切換到以下的畫面。點擊 『 Save Private Key 』按鈕，儲存 ppk 檔案。

點 Save private key 按鈕，保存 ppk 檔案。

顯示在 Public key 的文字就是公開金鑰的內容。點擊 『Load 』按鈕讀取 ppk 檔案可以再度顯示公開金鑰。

Push 時設定SSH連線，在右鍵選單中點擊『 TortoiseGit』 > 『push』，將會顯示以下畫面，請按『管理』按鈕。

點擊TortoiseGit > push，將會顯示下一個畫面，請按管理按鈕。

顯示以下畫面後，遠端為 origin，在『URL』 輸入 SSH 的路徑，在『Putty鑰』輸入剛才儲存的 ppk 檔案位置，點選 『增加/保存』 按鈕。在遠端目錄裡會增加origin，接著按『確認』按鈕。

在Putty認證指令上一步保存的ppk文檔，點選 增加/保存 按鈕。

Back To Top
設定SSH連接（Mac）
在應用程式目錄內開啟終端機，執行以下命令。

$ ssh-keygen
如果沒有要設定驗證密碼，請不要輸入任何文字，直接按『 Enter』 鍵即可。

如果沒有設定驗證密碼，請不要輸入任何文字直接輸入 Enter 鍵。

Generating public/private rsa key pair.
Enter file in which to save the key (/Users/eguchi/.ssh/id_rsa): <輸入 Enter 鍵>
Created directory '/Users/eguchi/.ssh'.
Enter passphrase (empty for no passphrase): <輸入驗證密碼>
Enter same passphrase again: <再輸入一次同樣的驗證密碼>
Your identification has been saved in /Users/eguchi/.ssh/id_rsa.
Your public key has been saved in /Users/eguchi/.ssh/id_rsa.pub.
The key fingerprint is:
57:15:3c:ca:f2:dc:27:6d:c2:9a:88:d0:70:cf:8d:31 eguchi@eguchi-no-MacBook-Air.local
The key's randomart image is:
+--[ RSA 2048]----+
|             .o. |
|             .o  |
|           ... . |
|      . . E.o    |
|       +So.O o . |
|      . ..+ + = +|
|       . . . o = |
|        . . o    |
|                 |
+-----------------+
執行以下命令就可以確認產生SSH連線所需要公開金鑰的內容。

```$ cat ~/.ssh/id_rsa.pub```
輸出實例

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDkkJvxyDVh9a+zH1f7ZQq/JEI79dVjDSG
4RzttQwfK+sgWEr0aAgfnxdxQeDKxIxqI1SwyTY8oCcWzvpORuPqwbc7UWWPcCvbQ3jlEdN
5jvwKM82hincEWwI3wzcnVg2Mn8dH86b5m6REDzwRgozQ3lqrgwGVlTvkHDFs6H0b/1PSrM
XGppOP/QXGEVhZ6Hy4m3b1wMjjrbYwmWIeYklgoGHyrldhAaDYc33y7aUcRyFyq5DubtsLn
2oj4K+1q36iviCHxCOri0FDmn2dzylRCI4S+A2/P7Y7rVfdT+8OWYKCBUs8lfjujghEtejq
Qmj9ikyGTEAW1zQCN7hVwYdjL hoge@hoge.local
接著在遠端數據庫裡設定公開金鑰。

Back To Top
設定SSH連接（主控台）
請執行以下命令。

```$ ssh-keygen```
接著會顯示以下的內容，在必要的地方輸入想要設定的驗證密碼，並按 『Enter 』鍵確認。

如果沒有要設定驗證密碼，請不要輸入任何文字，直接輸入『 Enter』 鍵即可。

Generating public/private rsa key pair.
Enter file in which to save the key (/Users/eguchi/.ssh/id_rsa): <輸入 Enter 鍵>
Created directory '/Users/eguchi/.ssh'.
Enter passphrase (empty for no passphrase): <輸入驗證密碼>
Enter same passphrase again: <再輸入一次同樣的驗證密碼>
Your identification has been saved in /Users/eguchi/.ssh/id_rsa.
Your public key has been saved in /Users/eguchi/.ssh/id_rsa.pub.
The key fingerprint is:
57:15:3c:ca:f2:dc:27:6d:c2:9a:88:d0:70:cf:8d:31 eguchi@eguchi-no-MacBook-Air.local
The key's randomart image is:
+--[ RSA 2048]----+
|             .o. |
|             .o  |
|           ... . |
|      . . E.o    |
|       +So.O o . |
|      . ..+ + = +|
|       . . . o = |
|        . . o    |
|                 |
+-----------------+
執行以下命令就可以確認產生SSH連線所需要公開金鑰的內容。

```$ cat ~/.ssh/id_rsa.pub```
輸出實例

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDkkJvxyDVh9a+zH1f7ZQq/JEI79dVjDSG
4RzttQwfK+sgWEr0aAgfnxdxQeDKxIxqI1SwyTY8oCcWzvpORuPqwbc7UWWPcCvbQ3jlEdN
5jvwKM82hincEWwI3wzcnVg2Mn8dH86b5m6REDzwRgozQ3lqrgwGVlTvkHDFs6H0b/1PSrM
XGppOP/QXGEVhZ6Hy4m3b1wMjjrbYwmWIeYklgoGHyrldhAaDYc33y7aUcRyFyq5DubtsLn
2oj4K+1q36iviCHxCOri0FDmn2dzylRCI4S+A2/P7Y7rVfdT+8OWYKCBUs8lfjujghEtejq
Qmj9ikyGTEAW1zQCN7hVwYdjL hoge@hoge.local
接著在遠端數據庫裡設定公開金鑰。

Back To Top
在貝格樂設定SSH公開金鑰
用戶登錄貝格樂後，請點選『 個人設定』。

點擊「個人設定」

在「個人設定」頁面，點選『 註冊您的SSH公用鑰匙』。

點擊「註冊SSH 公開鎖」

將SSH公開金鑰的內容複製貼上至編輯區，接著點擊『 登錄』按鈕。

粘帖SSH 公開鎖的內容，點擊「註冊」鍵

Back To Top

    
操作提交記錄
修改最近的提交記錄
只修改最近的提交記錄的註解
修改過去的提交記錄
只修改過去提交記錄的註解
中途停止rebase
查看HEAD的移動記錄
查看分支的移動記錄
刪除最近的提交
放棄rebase
取消最近的reset
複製在另一個分支的提交
查找包含特定註解的提交
修改最近的提交記錄
```$ git commit --amend```
執行 --amend ，可以覆蓋當前分支最前面的提交。

進階篇 【改寫提交】 修改最近的提交
進階篇 【教學3 改寫提交】 1. Commit --amend

Back To Top
只修改最近的提交記錄的註解
```$ git commit --amend```
在索引沒有註冊任何檔案的狀態之下，執行 --amend 重新提交，將會出現填寫註解的畫面，請在此修改註解。

進階篇 【改寫提交】 修改最近的提交
進階篇 【教學3 改寫提交】 1. Commit --amend

Back To Top
修改過去的提交記錄
```$ git rebase -i <commit>```
若指定一個提交紀錄後再執行此命令的話，會顯示提交清單的訊息。在其中找出要修改的提交將該行的 "pick" 的文字改成 "edit"，之後儲存並退出。

接著，編輯要修改的檔案，儲存檔案之後執行有 --amend 的提交。

```$ git commit --amend```
最後，加上 --continue 參數，執行 rebase 。

```$ git rebase --continue```
進階篇 【改寫提交】 改寫提交的歷史記錄
進階篇 【教程3 改寫提交】 6. 使用rebase -i 修改提交

Back To Top
只修改過去提交記錄的註解
```$ git rebase -i <commit>```
如果指定一個提交紀錄後再執行此命令的話，會顯示提交清單。在其中找出要修改的提交，將該行的 "pick"改成 "edit"，之後儲存並退出。

執行有 --amend 參數的提交。將會顯示填寫註解的畫面，請在此修改註解。

```$ git commit --amend```
最後，加上 --continue 參數，執行 rebase 。

```$ git rebase --continue```
進階篇 【改寫提交】 改寫提交的歷史記錄
進階篇 【教程3 改寫提交】 6. 使用rebase -i 修改提交

Back To Top
中途停止rebase
```$ git rebase --abort```
加上 --abort，即可以取消 rebase 。

Back To Top
查看HEAD的移動記錄
```$ git reflog```
執行 reflog 命令，就可以查看過去 HEAD 指向過去的提交清單。

08084a5 HEAD@{0}: commit: 添加pull的說明
99daed2 HEAD@{1}: commit: 添加commit的說明
48eec1d HEAD@{2}: checkout: moving from master to issue1
326fc9f HEAD@{3}: commit: 添加add的說明
48eec1d HEAD@{4}: commit (initial): first commit
這裡會顯示已刪除的提交和藉由 rebase 等所合併的提交。

Back To Top
查看分支的移動記錄
```$ git reflog <ref>```
在<ref> 指定分支名稱，並執行 reflog 命令，分支過去的提交清單會以下面的方式顯示。

445e0ae issue1@{0}: commit (merge): Merge branch 'master' into issue1
1c904bd issue1@{1}: commit (amend): 查看pull的講解
08084a5 issue1@{2}: commit: 添加pull的說明
99daed2 issue1@{3}: commit: 添加commit的說明
48eec1d issue1@{4}: branch: Created from 48eec1ddf73a7fb508ef664efd6b3d873631742f
這裡將會顯示已刪除的提交和藉著rebase等所匯集的提交。

Back To Top
刪除最近的提交
```$ git reset --hard HEAD~```
進階篇 【改寫提交】 放棄提交
進階篇 【教學3 改寫提交】 3. Reset

Back To Top
放棄rebase
```$ git reset --hard <commit>```
首先使用 reflog 命令查找 rebase 以前的提交，確認提交的雜湊值或「HEAD@{數字}」值。以下的記錄是 update2 提交之後，rebase 命令執行2個提交之後所合併的記錄。71bdfbd 以及 HEAD@{4} 是任意的提交。

a51f8d2 HEAD@{0}: rebase -i (finish): returning to refs/heads/dev
a51f8d2 HEAD@{1}: rebase -i (squash): update 1
3a273e1 HEAD@{2}: rebase -i (squash): updating HEAD
f55ef69 HEAD@{3}: checkout: moving from dev to f55ef69
71bdfbd HEAD@{4}: commit: update 2
f55ef69 HEAD@{5}: commit (amend): update 1
找到的雜湊值或「HEAD@{數字}」值填入 ，然後執行 reset 命令。

這就是把被 rebase 移動過的分支的前頭位置恢復到提交 rebase 之前的位置，藉此取消 rebase。

Back To Top
取消最近的reset
```$ git reset --hard ORIG_HEAD```
ORIG_HEAD是指reset之前的提交，您可以使用ORIG_HEAD復原之前的reset。

進階篇【改寫提交】 放棄提交
進階篇 【教學3 改寫提交】 3. Reset

Back To Top
複製在另一個分支的提交
```$ git cherry-pick "<commit>"```
把指定 <commit> 的提交複製到當前的分支。

進階篇 【改寫提交】 提取提交
進階篇 【教學3 改寫提交】 4. Cherry-pick

Back To Top
尋找包含特定註解的提交
```$ git log --grep "<pattern>"```
只顯示提交記錄裡包含 <pattern> 所指定文字的提交。

Back To Top

    
遠端操作
複製既有的遠端數據庫
添加一個遠端數據庫
顯示遠端數據庫清單
取遠端數據庫的分支建立本地端數據庫的分支
在遠端數據庫建立分支/push修改內容到分支
查看遠端數據庫分支的修改內容
合併遠端數據庫的分支的修改內容
刪除遠端數據庫的分支
在遠端數據庫建立標籤
刪除在遠端數據庫的標籤
修改已註冊的遠端數據庫的位址
修改已註冊的遠端數據庫名稱
複製既有的遠端數據庫
```$ git clone <url>```
執行 clone 命令時，會自動設定遠端數據庫為追踪目標。這樣在 push 或 fetch/pull 命令時即使省略 repository，也可以正確的顯示/讀取修改內容。

入門篇 【共享數據庫】 複製遠端數據庫
入門篇 【教學2 共享數據庫】 複製遠端數據庫

Back To Top
添加一個遠端數據庫
```$ git remote add <name> <url>```
Back To Top
顯示遠端數據庫清單
```$ git remote```
加上 -v 後即可顯示遠端數據庫的詳細情況。

Back To Top
取遠端數據庫的分支建立本地端數據庫的分支
```$ git checkout <branch>```
在最新的Git版本中，chekout 命令的參數下指定遠端數據庫的分支，就可以從遠端數據庫複製分支到本地端數據庫建立分支。
如果因為版本太舊不能建立，請按照下面的方法在 branch 命令下建立分支。

```$ git branch <branchname> origin/<branch>```
Back To Top
在遠端數據庫建立分支/push修改內容到分支
```$ git push <repository> <refspec>```
加上 -u ，可以將遠端數據庫的分支設為追蹤目標。這樣，在 push 或 fetch/pull 命令時即使省略 repository，也可以正確的顯示/讀取修改內容。

在 <repository>，除了 remote add 命令所添加的數據庫名稱以外，也可以直接指定 URL，省略 <repository> 也可以成為遠端數據庫指定的追踪對象。

在 <refspec> 可以指定分支名稱。省略 refspec 的話，遠端數據庫和本地端數據庫所存有的分支在預設裡會被列為目標。

入門篇 【共享數據庫】 Push到遠端數據庫
入門篇 【教學2 共享數據庫】 Push到遠端數據庫

Back To Top
查看遠端數據庫分支的修改內容
```$ git fetch <repository> <refspec>```
要確認遠端數據庫的修改內容，但不想合併內容到本地端數據庫時，可以使用 fetch 命令。fetch 命令不會修改本地端數據庫的分支。

可以省略 repository 或 refspec。省略 repository 時的動作與 push 的時候是相同的。省略 refspec，所有的分支在默認裡會被列為目標。

Back To Top
合併遠端數據庫的分支的修改內容
```$ git pull <repository> <refspec>```
藉著 pull 命令，可以把遠端數據庫修改的內容合併到本地端數據庫。您只要知道「pull = fetch + merge」就可以了。

可以省略 repository 或 refspec 。省略 repository 名稱時的動作與 push 的時候是相同的。若省略 refspec，會只pull現有的分支。

入門篇 【共享數據庫】 從遠端數據庫執行pull
入門篇 【教學2 共享數據庫】 從遠端數據庫執行pull

Back To Top
刪除遠端數據庫的分支
```$ git push --delete <repository> <branchname>```
在 push 命令加上 --delete 和 <repository> <branchname> ，然後執行。

Git 1.7之前的版本不能使用 --delete ，所以請用以下的指令：

```$ git push <repository> :<branchname>```
Back To Top
在遠端數據庫建立標籤
```$ git push --tags```
加上 --tags ，就可以將在本地端數據庫裡所有的標籤添加到遠端數據庫。

Back To Top
刪除在遠端數據庫的標籤
```$ git push --delete <repository> <tagname>```
在 push 命令加上 --delete 和 <repository> <tagname>，然後執行。

Git 1.7之前的版本不能使用 --delete ，所以請用以下的指令

```$ git push <repository> :<tagname>```
Back To Top
修改已註冊的遠端數據庫的位址
```$ git remote set-url <name> <newurl>```
在 <newurl> 內指定遠端數據庫的新地址。

Back To Top
修改已註冊的遠端數據庫名稱
```$ git remote rename <old> <new>```
將遠端數據庫的名稱從 <old> 改為 <new> 。

Back To Top

    
Git設定
設定用戶名稱/電子郵件
設定輸出顏色
設定命令的別名
忽略檔案使其不被管理
將空白目錄設定為管理對象
顯示設定清單
通過代理主機連接HTTP
通過需要用戶認證的代理主機連接HTTP
設定用戶名稱/電子郵件
```$ git config --global user.name <username>```
```$ git config --global user.email <mailaddress>```
不加上 --global的話，此設定只會對特定的數據庫有效。

Back To Top
設定輸出顏色
```$ git config --global color.ui auto```
Back To Top
設定命令的別名
```$ git config --global alias.<aliasname> <commandname>```
Back To Top
忽略檔案使其不被管理
$ echo <filename> >> .gitignore
將要忽略的檔案寫入至.gitignore製作忽略檔案清單。但是 .gitignore 本身是需要提交的。

Back To Top
將空白目錄設定為管理對象
$ cd <dirname>
```$ touch .gitkeep```
在Git，空白的目錄不是管理對象。因此您需要放一個檔案到目錄裡，任何檔案名稱都可以。
按照慣例使用 .gitkeep 為名稱比較多。

Back To Top
顯示設定清單
```$ git config --global --list```
Back To Top
通過代理主機連接HTTP
在 .gitconfig 檔案的http項目增加以下的設定:

[http]
proxy = <代理主機的電子郵件>:<代理主機的端口號碼>
您也可以使用​​以下config命令:

```$ git config --global http.proxy <代理主機的電子郵件>:<代理主機的端口號碼>```
Back To Top
通過需要用戶認證的代理主機連接HTTP
在 .gitconfig 檔案的http項目增加以下的設定:

[http]
proxy = http://<用戶名>:<密碼>@<代理主機的電子郵件>:<代理主機的端口號碼>
您也可以使用​​以下config命令:

```$ git config --global http.proxy http://<用戶名>:<密碼>@<代理主機的電子郵件>:<代理主機的端口號碼>```
Back To Top

    
Stash（暫存）
暫時儲存現狀的操作
顯示暫存清單
恢復暫存的操作
刪除暫存的操作
刪除所有暫存的操作
暫時儲存現狀的操作
$ git stash save
可以省略 save。也可以在 save 之後加入欲顯示的訊息。

Back To Top
顯示暫存清單
$ git stash list
Back To Top
恢復暫存的操作
$ git stash pop
僅使用"git stash pop" 將可復原到最新的操作。指定stash ID （如：stash@{1} ），則可以復原特定的操作。

Back To Top
刪除暫存的操作
$ git stash drop
如果使用 "git stash drop"，會刪除最新的操作。指定stash ID （如：stash@{1} ），則可以刪除特定的操作。

Back To Top
刪除所有暫存的操作
$ git stash clear
Back To Top

    
Git 和 Subversion的相比
Git和Subversion的命令比較表
Git和Subversion的命令比較表
Git和Subversion的命令比較表

操作	Git	Subversion
複製數據庫	git clone	svn checkout
提交	git commit	svn commit
查看提交的詳細記錄	git show	svn cat
確認狀態	git status	svn status
確認差異	git diff	svn diff
確認記錄	git log	svn log
增加	git add	svn add
移動	git mv	svn mv
刪除	git rm	svn rm
取消修改	git checkout / git reset	svn revert (※1)
建立分支	git branch	svn copy (※2)
切換分支	git checkout	svn switch
合併	git merge	svn merge
建立標籤	git tag	svn copy (※2)
更新	git pull / git fetch	svn update
上傳到遠端	git push	svn commit (※3)
忽視檔案清單	.gitignore	.svnignore
※1. SVN的 revert 是用來取消修改，但Git的 revert 是用來取消提交。即使是同樣的命令，在SVN和Git裡的含義是不同的。

※2. SVN的分支與標籤在構造上是相同的，但在Git上明顯是不一樣的。

※3. SVN沒有本地端數據庫/遠端數據庫的概念，所以一提交馬上就會上傳到在遠端裡。但Git的本地端數據庫和遠端數據庫的表現方法是不一樣的。

Back To Top

    
    疑難排解
SSH
用SSH連接遠端數據庫時會顯示”Permission denied (publickey).”
HTTPS
無法透過HTTPS URL 複製遠端數據庫
HTTPS執行push/pull時每次都需要密碼
SSH/HTTPS 共通
Push後，無法將變更上傳到遠端數據庫
用SSH連接遠端數據庫時會顯示”Permission denied (publickey).”
首先，請您先確認：

URL是否正確嗎？
本地端機器的私密金鑰（secret key )設定是否正確嗎？
遠端的公開金鑰設定是否正確嗎？
欲確認貝格樂數據庫的私密金鑰/公開金鑰的設定是否正確，請執行以下的命令：

```$ ssh <space>@<space>.git.backlogtool.com```
在 <space> 內設定特地位址。（例如您的貝格樂空間名稱為"demo.backlogtool.com" 您可以將其命名為 “demo@demo.git.backlogtool.com"。

設定正確的話，會出現以下的記錄。如果顯示錯誤的訊息，請再次查看以上的設定是否正確。

Hi yourname! You've successfully authenticated, but Backlog does not provide shell access.
Connection to git.backlog.jp closed.
Back To Top
無法透過HTTPS URL 複製遠端數據庫
如果您使用舊版本的Git，push 或 pull 有時可能不能正常運作。請使用1.7.10以後的版本。
使用 SourceTree 或 TortoiseGit 的用戶，請確認一下正在使用的版本。

Back To Top
HTTPS執行push/pull時每次都需要密碼
使用1.7.10以後版本的Git用戶，可以使用以下的方式，以避免每次都需要輸入密碼。

Windows
可以使用 git-credential-winstore ，您只需在第一次執行push/pull時輸入密碼。

Mac
在入門篇和進階篇都使用 Mac 的Git用戶，請注意，SourceTree具備了與Mac 鑰匙圈連接的功能。只要使用了這個功能，在 Pull 或 Push 時就不需要輸入密碼。

主控台
Mac用戶 ，您可以使用 Git credentials API 設定連接的用戶名/密碼。使用 Homebrew 的用戶在安裝Git時就會自動安裝Git credentials API。如果當時沒有安裝，則需要另外手動安裝。

您可以使用以下的命令來確認是否有安裝Git credentials API：

```$ git credential-osxkeychain```
Usage: git credential-osxkeychain <get|store|erase>
沒有安裝Git credentials API的話，會顯示以下的內容：

```$ git credential-osxkeychain```
git: 'credential-osxkeychain' is not a git command. See 'git --help'.
這種情形下，請立即下載並將檔案移至/usr/local/bin

```curl -s -O http://github-media-downloads.s3.amazonaws.com/osx/git-credential-osxkeychain```
chmod u+x git-credential-osxkeychain
mv git-credential-osxkeychain /usr/local/bin
完成安裝後，請執行以下命令來啟動Git credentials API

```git config --global credential.helper osxkeychain```
Back To Top
Push後，無法將變更上傳到遠端數據庫
這通常發生當您從新建的本地端數據庫進行push,接著會顯示以下的訊息：

```$ git push```
No refs in common and none specified; doing nothing.
Perhaps you should specify a branch such as 'master'.
Everything up-to-date
在 push 時省略分支名稱的話，Git在預設的情形下會認為您要push當前的變更到與本地端分支同樣名稱的遠端分支，這是因為在遠端數據庫上還未建立分支。因此如果要 push 到遠端數據庫裡不存在的分支，需要給予明確的數據庫與分支名稱。

```$ git push -u origin master```
一旦執行 push 後會自動建立 master 分支，接下來的 push 就可以省略數據庫和分支的名稱。

Back To Top
```
    
---
    
```
    目錄:

第 1 章 序章
1.1 認識版本控制 (version control)
1.2 可以用 Git 來管理的程式
1.3 操作 Git 的各種工具
1.4 取得 Git
1.5 完成個人資料設定

第 2 章 建立儲存庫 (Repository) 並用 Git 開始管控
2.1 建立 GitHub 雲端儲存庫
2.2 建立本機儲存庫
2.3 在任一本機儲存庫建立程式, 開始用 Git 管控
2.4 從其他本機儲存庫 pull 異動
2.5 push mine, pull yours 的操作演練
2.6 commit 的相關建議

第 3 章 五個 Git 常用區域以及分支 (Branches) 概念
3.1 使用 Git 的 5 個關鍵區域
3.2 分支 (Branches) 功能
3.3 儲存庫的延伸操作

第 4 章 檢視 commits 內容並合併 (merge) 分支
4.1 合併前檢視 commits 內容
4.2 透過 GUI 工具合併分支
4.3 解決合併時發生的衝突 (conflict)
4.4 認識合併時的 Git 訊息
4.5 避免合併衝突的幾個建議
4.6 利用 GitHub 的 Pull Request 功能完成多人協同檢視、合併 
4.7 協同開發實戰觀摩

第 5 章 rebase、amend 和 cherry-pick 指令
5.1 rebase 合併功能
5.2 用 amend 修正 commit 的內容
5.3 用 cherry-pick 做選擇性合併
5.4 綜合演練

第 6 章 用 Interactive rebase 修改 commit 歷史紀錄
6.1 在程式開發工作中使用Interactive rebase
6.2 Interactive rebase 實戰觀摩

第 7 章 製作儲存庫副本 (mirror)、notes 與 tag 等實用指令
7.1 製作儲存庫副本
7.2 利用 notes 指令添加 commit 的說明
7.3 使用 tag 指令註記關鍵的 commit

第 8 章 建立指令的別名 (alias)
8.1 alias 指令的使用介紹
8.2 查看建立 alias 後的 config 檔內容

第 9 章 log 指令的進階用法
9.1 備妥 LogDemo 範例程式
9.2 各種實用的 log 指令參數
9.3 自訂 log、show 所顯示的參考資訊

第 10 章 用 stash 指令把工作存入暫存區
10.1 便利的 git stash 暫存機制
10.2 用 clean 指令清除工作區的異動內容

第 11 章 用 bisect 和 blame 指令揪出有問題的 commit
11.1 用 git bisect 找出 bug 源頭
11.2 用 git blame 列出逐行修改軌跡

第 12 章 回復內容、檔案救援…等常見 Git 使用問題
12.1 commit 的訊息寫錯了
12.2 剛送出的 commit 中忘記加入變更的檔案
12.3 想要撤銷 (undo) 先前送出的 commit
12.4 分支的名字取錯了
12.5 不小心將異動內容 commit 到錯誤的分支
12.6 發現誤刪檔案, 而且老早就送出 commit 了...
12.7 回復到先前某個 commit 時間點的檔案內容
```
    
    
```
目錄大綱
Chapter 1

什麼是 GitHub? 現代開發者不能不知道的協同合作平台

全世界最大的原始碼管理平台與開放原始碼群

GitHub 如何實現現代化應用程式開發

GitHub 相關服務與費用

註冊GitHub 帳號

為您的帳號啟用雙因子驗證

 

Chapter 2

Git 基礎入門

什麼是Git? 為什麼要學Git

Git 檔案運作原理

Git 快速上手

Git 最佳實踐

 

Chapter 3

GitHub 基本功能介紹與介面說明

GitHub 操作介面介紹 - 初學者也能輕鬆上手

開始您的第一個 Repository

豐富您的專案介紹 - GitHub shields

建立工作的第一步 – Issue 與Label

團隊討論專業技巧 - Autolinked references 與Permanent link

快速回覆的好幫手 - Saved Replies

流程管理的重要功能 – Label

文件管理功能 – Wiki

為您的 Repository 建立社群論壇 - Discussions

專案管理 – GitHub Projects

 

Chapter 4

GitHub 與 DevOps

DevOps 流程參考實現

Branch 管理與策略

GitHub flow 與Fork Workflow

程式發行管理 – Tag 與 Release

 

Chapter 5

GitHub 持續整合與持續佈署

開始自動化工作流程的第一步 - GitHub Actions

Workflow 語意解析

觸發Workflow 重要設定 - Event

進階YAML 技巧 - 環境變數 (Environment Variables) 與秘密 (Secrets)

實作持續整合 - 以ASP.NET Core 專案為例

實作持續整合 - 以ASP.NET 專案(.NET Framework) 為例

實作持續交付 – 將ASP.NET Core 部署至Azure App Service

實作持續交付 – 將ASP.NET 應用程式(.NET Framework) 部署

至Azure App Service

常見持續部署架構與自訂代理程式 (Self-hosted runner)

實作持續交付 – 將ASP.NET 網頁應用程式部署至 IIS

 

Chapter 6

GitHub 安全管理

基本安全相關功能介紹

程式碼與秘密掃描

GitHub Action Security 最佳實踐

Commit signature verification - 確定每次變更來源是可以信任的

 

Chapter 7

GitHub 多元應用

靜態網頁服務 - GitHub Page

整潔的程式碼區塊 - GitHub Gists

完美的個人履歷 - 透過README.md 建立個人儀錶板    
```
