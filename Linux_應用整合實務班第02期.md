###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 課程資訊

* 課程名稱: Linux 應用整合實務班 第 02 期
* 報名連結: [
台灣就業通 在聯訓練網](https://ojt.wda.gov.tw/ClassSearch/Detail?OCID=143725&plantype=1)
* 訓練單位: 全國勞工聯合總工會
* 講師: 廖子儀
    * 認證: RHCA Level II, LPIC Level 2, Comptia Security+, Comptia CySA+
    * 專長: 企業 Linux 應用導入規劃, 資訊系統整合建置, Open Source 虛擬化規劃與執行, PHP程式設計

## 課程大綱

本課程讓學員瞭解如何使用 Linux 作業系統進行常見的整合機制。

在本課程中，主要內容包含：

| -- | 項目 | 講師 |
| -- | -- | -- |
| 2022-07-10 | 企業營運需求與 Linux 整合概觀 | 廖子儀 |
| 2022-07-10 | 企業版 Linux 選擇與使用 | 廖子儀 |
| 2022-07-17 | Linux 檔案系統與 Windows 檔案分享 | 廖子儀 |
| 2022-07-17 | Linux 檔案分享與 Windows AD 帳號整合 | 廖子儀 |
| 2022-07-24 | Linux 檔案系統卷建立與管理 | 廖子儀 |
| 2022-07-24 | Linux 檔案系統卷快照應用 | 廖子儀 |
| 2022-07-31 | Linux Container容器部署 | 廖子儀 |
| 2022-07-31 | Container 應用與 NFS 儲存管理 | 廖子儀 |
| 2022-08-07 | 反向代理服務應用 – 搭配容器應用 | 廖子儀 |
| 2022-08-07 | 反向代理服務應用 – SSL 憑證與加密 | 廖子儀 |
| 2022-08-14 | MySQL/MariaDB 資料庫 - 調整與設定 | 廖子儀 |
| 2022-08-14 | MySQL/MariaDB 資料庫 – 資料同步作業 | 廖子儀 |
| 2022-08-21 | Linux 應用整合驗收 | 廖子儀 |
| 2022-08-21 | Linux 應用整合案例研究 | 廖子儀 |

## 應用工具

課程應用工具如下：

* [AlmaLinux 8.4](https://rsync.repo.almalinux.org/vault/8.4/isos/x86_64/AlmaLinux-8.4-x86_64-dvd.iso)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`
 

---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 線上資源

* [Google Meet](https://meet.google.com/uta-wkjq-vfd) (https://meet.google.com/uta-wkjq-vfd)
* [撥放清單](https://www.youtube.com/playlist?list=PLi8AVVmcS1cLRHmzY4e6vUXSRkLK0syk2)

## 上課環境

* 上課環境會提供遠端主機。請大家操作的電腦確認符合下列規格：

    * **Windows 10/11** 版本，以連線遠端桌面。
    * macOS 請安裝 **Microsoft Remote Desktop** APP (https://apps.apple.com/tw/app/microsoft-remote-desktop/id1295203466?mt=12)

* 遠距上課使用 Google Meet，建議使用 Google Chrome 進行連線。

## Google Meet 測試

1. 點選會議連結後，選擇 [檢查音訊及視訊功能]

    ![](https://i.imgur.com/wsFlVrT.png)

2. 開啟視訊、喇叭等功能

    ![](https://i.imgur.com/r7IOJEL.jpg)

3. 測試各功能是否正常，如果正常則可以順利看到測試錄影結果

    ![](https://i.imgur.com/EghtxuC.jpg)

4. 確認各功能正常後，在上課前點選要求進入會議室

    ![](https://i.imgur.com/xqX0TkF.jpg)

 
###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`

---
tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`
---

# Kickstart 自動安裝

![](https://i.imgur.com/TRnJHxR.png)


安裝完成後重新開機

![](https://i.imgur.com/nOGIWgd.png)

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`



---
tags: `全勞聯_Linux-Integration-02` `全國勞工聯合總工會`
---

# 設定 Kickstart Server

## 設定 KS 檔

@Desktop

```
student$ sudo su -

root#
```

```
root# dnf install -y httpd

root# systemctl enable --now httpd

root# firewall-cmd --permanent --add-service=http
root# firewall-cmd --reload
```

```
root# cd /var/www/html/

root# mkdir ks/; cd ks/
root# scp root@172.16.170.1X:~/anaconda-ks.cfg ./myks.ks

root# restorecon -R /var/www/html/
root# chmod +r ./myks.ks
```

Firefox: http://localhost/ks/myks.ks

![](https://i.imgur.com/tYdbjX5.png)

## 設定 BaseOS

@Desktop

```
root# umount /dev/sr0
```

```
root# cd /var/www/html/
root# cd ks/

root# mkdir OS
root# mount /dev/sr0 /var/www/html/ks/OS/

root# ls OS/
```

![](https://i.imgur.com/0PR7Tpi.png)

Firefox: http://172.16.170.X/ks/OS/BaseOS/

![](https://i.imgur.com/NtrE7Iu.png)

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`



---
tags: `全勞聯_Linux-Integration-02` `全國勞工聯合總工會`
---

# 設定 Kickstart Server

## 設定 KS 檔

@Desktop

```
student$ sudo su -

root#
```

```
root# dnf install -y httpd

root# systemctl enable --now httpd

root# firewall-cmd --permanent --add-service=http
root# firewall-cmd --reload
```

```
root# cd /var/www/html/

root# mkdir ks/; cd ks/
root# scp root@172.16.170.1X:~/anaconda-ks.cfg ./myks.ks

root# restorecon -R /var/www/html/
root# chmod +r ./myks.ks
```

Firefox: http://localhost/ks/myks.ks

![](https://i.imgur.com/tYdbjX5.png)

## 設定 BaseOS

@Desktop

```
root# umount /dev/sr0
```

```
root# cd /var/www/html/
root# cd ks/

root# mkdir OS
root# mount /dev/sr0 /var/www/html/ks/OS/

root# ls OS/
```

![](https://i.imgur.com/0PR7Tpi.png)

Firefox: http://172.16.170.X/ks/OS/BaseOS/

![](https://i.imgur.com/NtrE7Iu.png)

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 編輯 myks.ks

@Desktop

```
root# cd /var/www/html/ks/

root# cp myks.ks myks.ks_backup
```

```
root# vi myks.ks
```

```=
修改
...

L12:
chrony

L26,L27
#url --url="http://172.16.60.253/alma8/repo/BaseOS/"
url --url="http://172.16.170.X/ks/OS/BaseOS/"
```

```
root# diff myks.ks myks.ks_backup
```

![](https://i.imgur.com/Y2l3P0w.png)

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 使用 myks.ks 安裝

## 清空 Server

@Server

```
root# dd if=/dev/zero of=/dev/vda bs=1M count=10
```

```
root# reboot
```

## 重新安裝 Server

1. 開啟 Open-Console
2. 設定參考的 Kickstart

    ```
    inst.ks=http://172.16.170.X/ks/myks.ks
    ```

## 驗證

@Server

```
root# dnf list chrony
```

![](https://i.imgur.com/2hIkEnx.png)


## 參考

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html-single/performing_an_advanced_rhel_8_installation/index

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 校時

@Server

```
root# chronyc sources
FAIL!

root# systemctl enable --now chronyd

root# chronyc sources
```

@Desktop

```
root# systemctl enable --now chronyd

root# chronyc sources
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 清除 SSH KEY

@Desktop

```
student$ rm ~/.ssh/known_hosts

student$ student$172.16.170.1X
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Linux UGO

![](https://i.imgur.com/tgzlIqu.png)


## 練習

條件:

* /data/project1 只能 owner/group 有完整權限，其它人沒任何權限
* /data/public 大家都能讀寫

@Server

```
root# mkdir /data/; cd /data/

root# mkdir project1 public
root# ls -lh
```

新增群組

```
root# groupadd grp1
root# groupadd grp2
root# getent group
```

設定 project1 權限

```
root# ls -lh
root# chgrp -R grp1 project1/
root# ls -lh

root# chmod g=rwx,o=--- project1/
root# ls -lh
```

設定 public 權限

```
root# chmod 777 public/
root# ls -lh
```

新增使用者與群組對應

```
root# useradd -g grp1 user11
root# useradd -g grp1 user12
root# useradd -g grp2 user21
root# useradd -g grp2 user22

root# id user11
root# id user12
root# id user21
root# id user22
```

使用 user11, user21 驗證目錄權限

```
root# su - user11
user11$ cd /data/
user11$ ls -lh
user11$ id

user11$ echo hello > project1/user11
user11$ ls -lh project1/user11 

user11$ echo hello > public/user11
user11$ cat public/user11

user11$ exit

root#
```

```
root# su - user21
user21$ cd /data/
user21$ ls -lh

user21$ cat project1/user11
FAIL!

user21$ cd project1/
FAIL!

user21$ echo Hello > project1/user21
FAIL!

user21$ echo Hello > public/user21
user21$ cat public/user21 

user21$ ls -lh project1/
FAIL!

user21$ exit

root#
```

```
root# ls -lh project1/
root# ls -lh public/
```

> ![](https://i.imgur.com/EdtOLyA.png)

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


# 設定 Samba

條件:

    * project1 只能 grp1 群組 有完整權限，其它人沒任何權限
    * public 大家都能讀寫


@Server

## 安裝套件與基本設定

```
root# dnf install -y samba
```

```
root# cp -a /etc/samba/smb.conf{,_backup}
```

```
root# vi /etc/samba/smb.conf
```

```=
最後新增
...

[class-share]
    comment = SHARE
    path = /data
    public = no
    writable = yes
    printable = no
    create mask = 0660
    directory mask = 0770
```

```
root# systemctl enable --now smb

root# firewall-cmd --permanent --add-service=samba
root# firewall-cmd --reload
root# firewall-cmd --list-all
```

```
root# chcon -t samba_share_t -R /data
```

## 設定使用者帳號

@Server

```
root# smbpasswd -a user11
root# smbpasswd -a user12
root# smbpasswd -a user21
root# smbpasswd -a user22
```

## 驗證

@Desktop

1. 開啟 **Files**

    ![](https://i.imgur.com/Jp48Ynk.png)

3. 在 [Other Locations] 輸入:

    smb://172.16.170.1X
    
    ![](https://i.imgur.com/jcuBdSa.png)
    
    ![](https://i.imgur.com/ZxjFhHV.png)

    
3. 輸入帳號密碼驗證

    使用 `user11` 驗證。

    * 不要記錄密碼。

    ![](https://i.imgur.com/mjdNyF1.png)

4. 重複執行 第 3. 使用 `user21` 驗證。

## Sticky bit

* 防止誤刪其它帳號的檔案

@Desktop

1. 使用 `user11` 在 `public` 中建立文字檔案，名為 `user11.txt`。
2. 在 Server 中查看 `public` 中的權限。
3. 使用 `user21` 在 `public` 中打開 `user11.txt`。

    FAIL!
    
4. 刪除 `public` 中的 `user11.txt`。

    `user11.txt` 會被刪除。

@Server

```
root# chmod 1777 /data/public/

root# ls -lh /data/
```

@Desktop

1. 使用 `user11` 在 `public` 中建立文字檔案，名為 `user11.txt`。
2. 在 Server 中查看 `public` 中的權限。
3. 使用 `user21` 在 `public` 中打開 `user11.txt`。

    FAIL!
    
4. 刪除 `public` 中的 `user11.txt`。

    FAIL!
    
## 查看線上登入帳號

@Server

```
root# smbstatus 

Samba version 4.14.5
PID     Username     Group        Machine                                   Protocol Version  Encryption           Signing              
----------------------------------------------------------------------------------------------------------------------------------------
11268   nobody       nobody        (ipv4:172.16.170.5:46154)                SMB3_11           -                    -                    
10954   nobody       nobody        (ipv4:172.16.170.5:46030)                SMB3_11           -                    -                    
11272   user21       grp2         172.16.170.5 (ipv4:172.16.170.5:41976)    SMB3_11           -                    AES-128-CMAC         

Service      pid     Machine       Connected at                     Encryption   Signing     
---------------------------------------------------------------------------------------------
class-share  11272   172.16.170.5  Sun Jul 17 09:15:43 PM 2022 CST  -            AES-128-CMAC
IPC$         11268                 Sun Jul 17 09:13:24 PM 2022 CST  -            -           
IPC$         10954                 Sun Jul 17 07:34:09 PM 2022 CST  -            -           

No locked files
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


# Linux ACL

* `grp3` 可讀取 `/data/project1/` 裡的檔案與目錄內容。

## ACL 設定

@Server

```
root# cd /data/
```

```
root# groupadd grp3
```

```
root# getfacl project1

root# setfacl -R -m g:grp3:r-x project1

root# getfacl project1

root# setfacl -R -m d:g:grp3:r-x project1

root# getfacl project1
```

```
root# useradd -g grp3 user31
root# useradd -g grp3 user32

root# smbpasswd -a user31
root# smbpasswd -a user32
```

## 驗證

@Desktop

1. 使用 `user31` 登入 SMB 服務
2. `user31` 應能讀取 `project1` 內容
3. `user31` 應能存取 `public` 內容

## 綜合應用

### 新增帳號進入 ACL

* 設定 `user21` 可讀取 `project1` 目錄與其內容。

    @Server

    ```
    root# getfacl /data/project1/
    
    root# setfacl -R -m u:user21:r-x /data/project1/
    root# setfacl -R -m d:u:user21:r-x /data/project1/
    
    root# getfacl /data/project1/
    ```
    
    @Desktop
    
    使用 `user21` 登入應可讀取 `project1` 目錄與其檔案內容。

### 去除帳號 ACL

* 去除 `user21` 對 `project1` 目錄的所有權限。

    @Server

    ```
    root# getfacl /data/project1/
    
    root# setfacl -R -x u:user21 /data/project1/
    root# setfacl -R -x d:u:user21 /data/project1/
    
    root# getfacl /data/project1/
    ```
    
    @Desktop

    使用 `user21` 登入不可讀取 `project1` 目錄與其檔案內容。

### 去除所有 ACL 權限。

* 去除 所有 對 `project1` 目錄的所有 ACL 權限。

   @Server

    ```
    root# getfacl /data/project1/
    
    root# setfacl -R -b /data/project1/
    
    root# getfacl /data/project1/
    ```
    
    @Desktop

    使用 `user31` 無法讀取 `project1` 目錄與其檔案內容。
    
## 參考文件

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/configuring_basic_system_settings/assembly_managing-access-control-list_configuring-basic-system-settings#displaying-the-current-acl_assembly_managing-access-control-list

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 與 AD 整合

請先完成校時作業。

https://hackmd.io/@esys/B1kBWK_q9/%2FNDpWNIEgQlWFIzD5GJIsYg

@Server

## 1. 設定加密支援

```
root# update-crypto-policies --set DEFAULT:AD-SUPPORT

root# reboot
```

## 2. 安裝套件

```
root# yum install realmd oddjob-mkhomedir oddjob samba-winbind-clients samba-winbind samba-common-tools samba-winbind-krb5-locator

root# yum install samba

root# mv /etc/samba/smb.conf /etc/samba/smb.conf.bak
```

## 3. 加入 AD

```
root# realm join -h
```

```
root# realm join --membership-software=samba --client-software=winbind linux.class -U adadmin
```

## 4. 查看帳號

```
root# wbinfo -u

root# wbinfo -g
```

```
root# id 'LINUX\useryy'
```

![](https://i.imgur.com/PLFEdhk.png)


## Ref

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/integrating_rhel_systems_directly_with_windows_active_directory/connecting-rhel-systems-directly-to-ad-using-samba-winbind_integrating-rhel-systems-directly-with-active-directory

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# AD + Samba LAB

![](https://i.imgur.com/oRyNBGB.png)

## 整合

@Server

```
root# lsblk 
root# mkfs.xfs /dev/sdb

root# blkid /dev/sdb
/dev/sdb: UUID="e543b838-b6ea-4030-abec-ec5715e23c10" BLOCK_SIZE="512" TYPE="xfs"
```

> 記錄 `UUID`

```
root# mkdir /data
root# cd /etc
root# cp -a fstab{,_backup}
```

```
root# vi fstab
```

```=
最後一行新增
...

UUID=e543b838-b6ea-4030-abec-ec5715e23c10 /data xfs defaults 0 0
```

> UUID 為使用 `blkid` 查到的值

```
root# mount -a
root# df -h
```

> 如 mount -a 出錯則不要往下

```
root# cd /etc/samba/

root# cp -a smb.conf{,_ad}
```

```
root# vi smb.conf
```

```=
最後新增
...

[Projects]
    comment = Class Projects
    path = /data/projects
    public = no
    writable = yes
    printable = no
    create mask = 0660
    directory mask = 0770

[Public]
    comment = Class Public
    path = /data/public
    public = no
    writable = yes
    printable = no
    create mask = 0660
    directory mask = 0770

```

設定權限

```

root# cd /data/

root# mkdir projects public

root# chmod 770 *

root# setfacl -R -m g:"LINUX\\grp13":rwx projects/
root# setfacl -R -m d:g:"LINUX\\grp13":rwx projects/
root# setfacl -R -m g:"LINUX\\grp15":rwx projects/
root# setfacl -R -m d:g:"LINUX\\grp15":rwx projects/

root# setfacl -R -m g:"LINUX\\grp12":r-x projects/
root# setfacl -R -m d:g:"LINUX\\grp12":r-x projects/
root# getfacl projects/
```

```
root# getfacl public/

root# for g in {11..19}
> do
> setfacl -R -m g:"LINUX\\grp${g}":rwx public/
> setfacl -R -m d:g:"LINUX\\grp${g}":rwx public/
> done

root# getfacl public/
```

```
root# chcon -t samba_share_t -R /data/
```

啟用 samba 服務

```
root# systemctl enable --now smb

root# testparm 

root# firewall-cmd --permanent --add-service=samba
root# firewall-cmd --reload
```

## 測試

@Desktop

1. `grp13` 測試

    1. 使用 `LINUX\user37` 登入 smb://172.16.170.1X。
    2. `project` 應能讀寫。
    3. `public` 應能讀寫。

2. `grp12` 測試

    1. 使用 `LINUX\user28` 登入 smb://172.16.170.1X。
    2. `project` 應只能讀取。
    3. `public` 應能讀寫。

3. `grp16` 測試

    1. 使用 `LINUX\user63` 登入 smb://172.16.170.1X。
    2. `project` 無法存取。
    3. `public` 應能讀寫。

3. `grp15` 測試

    1. 使用 `LINUX\user59` 登入 smb://172.16.170.1X。
    2. `project` 應能讀寫。
    3. `public` 應能讀寫。

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 磁碟分割

@Server

```
root# lsblk /dev/sdb

root# blkid /dev/sdb
```

```
root# gdisk /dev/sdb
FAIL!

root# dnf install -y gdisk
```

## 建立 Partition

* 使用 GPT 格式
* /dev/sdb1: 1GB, Code 8300
* /dev/sdb2: 1GB, Code 8300

建立 /dev/sdb1

```
root# gdisk /dev/sdb
GPT fdisk (gdisk) version 1.0.3

Partition table scan:
  MBR: not present
  BSD: not present
  APM: not present
  GPT: not present

Creating new GPT entries.

Command (? for help): n (輸入 n)
Partition number (1-128, default 1): 
First sector (34-8388574, default = 2048) or {+-}size{KMGTP}: 1G
Last sector (2097152-8388574, default = 8388574) or {+-}size{KMGTP}: ^C
[root@c170-server-teacher ~]# gdisk /dev/sdb
GPT fdisk (gdisk) version 1.0.3

Partition table scan:
  MBR: not present
  BSD: not present
  APM: not present
  GPT: not present

Creating new GPT entries.

Command (? for help): n
Partition number (1-128, default 1): (直接 [Enter])
First sector (34-8388574, default = 2048) or {+-}size{KMGTP}: (直接 [Enter])
Last sector (2048-8388574, default = 8388574) or {+-}size{KMGTP}: +1G
Current type is 'Linux filesystem'
Hex code or GUID (L to show codes, Enter = 8300): L
0700 Microsoft basic data  0c01 Microsoft reserved    2700 Windows RE          
3000 ONIE boot             3001 ONIE config           3900 Plan 9              
4100 PowerPC PReP boot     4200 Windows LDM data      4201 Windows LDM metadata
4202 Windows Storage Spac  7501 IBM GPFS              7f00 ChromeOS kernel     
7f01 ChromeOS root         7f02 ChromeOS reserved     8200 Linux swap          
8300 Linux filesystem      8301 Linux reserved        8302 Linux /home         
8303 Linux x86 root (/)    8304 Linux x86-64 root (/  8305 Linux ARM64 root (/)
8306 Linux /srv            8307 Linux ARM32 root (/)  8400 Intel Rapid Start   
8e00 Linux LVM             a000 Android bootloader    a001 Android bootloader 2
a002 Android boot          a003 Android recovery      a004 Android misc        
a005 Android metadata      a006 Android system        a007 Android cache       
a008 Android data          a009 Android persistent    a00a Android factory     
a00b Android fastboot/ter  a00c Android OEM           a500 FreeBSD disklabel   
a501 FreeBSD boot          a502 FreeBSD swap          a503 FreeBSD UFS         
a504 FreeBSD ZFS           a505 FreeBSD Vinum/RAID    a580 Midnight BSD data   
a581 Midnight BSD boot     a582 Midnight BSD swap     a583 Midnight BSD UFS    
a584 Midnight BSD ZFS      a585 Midnight BSD Vinum    a600 OpenBSD disklabel   
a800 Apple UFS             a901 NetBSD swap           a902 NetBSD FFS          
a903 NetBSD LFS            a904 NetBSD concatenated   a905 NetBSD encrypted    
a906 NetBSD RAID           ab00 Recovery HD           af00 Apple HFS/HFS+      
af01 Apple RAID            af02 Apple RAID offline    af03 Apple label         
Press the <Enter> key to see more codes: 8300 (輸入 8300)
Hex code or GUID (L to show codes, Enter = 8300):  
Changed type of partition to 'Linux filesystem'

Command (? for help): p (輸入 p)
Disk /dev/sdb: 8388608 sectors, 4.0 GiB
Model: QEMU HARDDISK   
Sector size (logical/physical): 512/512 bytes
Disk identifier (GUID): BE588C80-A46A-49EB-9BBE-82CA23F07053
Partition table holds up to 128 entries
Main partition table begins at sector 2 and ends at sector 33
First usable sector is 34, last usable sector is 8388574
Partitions will be aligned on 2048-sector boundaries
Total free space is 6291389 sectors (3.0 GiB)

Number  Start (sector)    End (sector)  Size       Code  Name
   1            2048         2099199   1024.0 MiB  8300  Linux filesystem

Command (? for help): w (輸入 w)

Final checks complete. About to write GPT data. THIS WILL OVERWRITE EXISTING
PARTITIONS!!

Do you want to proceed? (Y/N): Y (輸入 Y)
OK; writing new GUID partition table (GPT) to /dev/sdb.
The operation has completed successfully.
```

```
root# gdisk /dev/sdb -l
```

新增 /dev/sdb2

```
root# gdisk /dev/sdb
GPT fdisk (gdisk) version 1.0.3

Partition table scan:
  MBR: protective
  BSD: not present
  APM: not present
  GPT: present

Found valid GPT with protective MBR; using GPT.

Command (? for help): n
Partition number (2-128, default 2): 
First sector (34-8388574, default = 2099200) or {+-}size{KMGTP}: 
Last sector (2099200-8388574, default = 8388574) or {+-}size{KMGTP}: +1G
Current type is 'Linux filesystem'
Hex code or GUID (L to show codes, Enter = 8300): 
Changed type of partition to 'Linux filesystem'

Command (? for help): p
Disk /dev/sdb: 8388608 sectors, 4.0 GiB
Model: QEMU HARDDISK   
Sector size (logical/physical): 512/512 bytes
Disk identifier (GUID): BE588C80-A46A-49EB-9BBE-82CA23F07053
Partition table holds up to 128 entries
Main partition table begins at sector 2 and ends at sector 33
First usable sector is 34, last usable sector is 8388574
Partitions will be aligned on 2048-sector boundaries
Total free space is 4194237 sectors (2.0 GiB)

Number  Start (sector)    End (sector)  Size       Code  Name
   1            2048         2099199   1024.0 MiB  8300  Linux filesystem
   2         2099200         4196351   1024.0 MiB  8300  Linux filesystem

Command (? for help): w

Final checks complete. About to write GPT data. THIS WILL OVERWRITE EXISTING
PARTITIONS!!

Do you want to proceed? (Y/N): Y
OK; writing new GUID partition table (GPT) to /dev/sdb.
The operation has completed successfully.
```

```
root# gdisk -l /dev/sdb
```

![](https://i.imgur.com/43VGuAb.png)

```
root# lsblk /dev/sdb
```

![](https://i.imgur.com/rWDU0gA.png)

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# XFS 磁碟使用

@Server

```
root# blkid /dev/sdb1

root# mkfs.xfs /dev/sdb1

root# blkid /dev/sdb1
```

> 記錄 UUID

```
root# mkdir /data/sdb1
root# mkdir -p /data/sdb1
```

```
root# cd /etc/
root# cp -a fstab fstab_backup
```

```
root# vi fstab
```

```=
最後新增
...

UUID=d3faab54-4c6e-48c6-b1d1-4a4f4fdc7993 /data/sdb1 xfs defaults 0 0
```

> UUID 須為 sdb1 的代碼

```
root# df /data/sdb1
root# mount -a
root# df /data/sdb1
```

```
root# mkfs.xfs /dev/sdb2 
root# blkid /dev/sdb2
```

> 記錄 UUID

```
root# mkdir /data/sdb2
```

```
root# vi /etc/fstab
```

```=
最後新增
...

UUID=bea5d7ef-5968-4b5f-9ab7-2617abcb50f1 /data/sdb2 xfs defaults 0 0
```

> UUID 須為 sdb2 的代碼

```
root# df /data/sdb2
root# mount -a
root# df /data/sdb2
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 開機掛載

@Server

```
root# reboot
```

```
root# df -h
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        890M     0  890M   0% /dev
tmpfs           908M     0  908M   0% /dev/shm
tmpfs           908M   25M  883M   3% /run
tmpfs           908M     0  908M   0% /sys/fs/cgroup
/dev/sda3        17G  1.5G   16G   9% /
/dev/sdb2      1014M   40M  975M   4% /data/sdb2
/dev/sdb1      1014M   40M  975M   4% /data/sdb1
/dev/sda1      1014M  189M  826M  19% /boot
tmpfs           182M     0  182M   0% /run/user/0
```


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`



---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# SWAP Disk

@Server

```
root# vi /etc/fstab
```

```=
去除 /dev/sdb2, 註解原 swap
...


#UUID=c7816b98-3b42-44d0-b00c-68c5649f3fcf none swap efaults 0 0
```

```
root# free -m
root# tail /etc/fstab
```

```
root# umount /data/sdb2

root# dd if=/dev/zero of=/dev/sdb2 bs=1M count=100
root# gdisk -l /dev/sdb
```

```
root# gdisk /dev/sdb
```

```
t (修改 Code)
2 (第 2 個 Partition)
8200 (設為 SWAP)
w (寫入 Disk)
Y (確定修改)
```

```
root# gdisk -l /dev/sdb

root# reboot
```

```
root# free -m

root# mkswap /dev/sdb2
```

```
root# blkid /dev/sdb2
```

![](https://i.imgur.com/VahYr43.png)

> 找出 UUID

```
root# vi /etc/fstab
```

```
新增 swap 設定
...

UUID=ea4387ea-ab63-4349-aee0-a5a6582d6091 none swap defaults 0 0
```

```
root# mount -a
root# free -m
```

> mount -a 不會處理 swap

```
root# swapon /dev/sdb2

root# free -m
root# lsblk 

root# swapon -s
```

![](https://i.imgur.com/mLaPVsW.png)

```
root# reboot
```

```
root# free -m
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 清除作業

@Server

```
root# cat /etc/fstab_backup > /etc/fstab

root# swapoff /dev/sdb2

root# dd if=/dev/zero of=/dev/sdb bs=1M count=100
```

```
root# reboot
```

```
root# df -h
root# free -m
root# lsblk
```

![](https://i.imgur.com/mRM3ora.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 磁碟複製

@Server

```
root# df -h /data/sdb1
```

```
root# cd /data/sdb1/

root# touch file-{1..10}

root# ls -lh 
```

```
root# cd

root# umount /data/sdb1/
```

```
root# cd 

root# dd if=/dev/sdb1 of=sdb1.img bs=1M status=progress

root# ls -lh sdb1.img
root# file sdb1.img
```

```
root# df -h /mnt

root# mount -o ro sdb1.img /mnt

root# df -h /mnt

root# ls -lh /mnt
```

![](https://i.imgur.com/kvmv5cz.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`




---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# LVM 管理與使用

@Server

```
root# lsblk
```

```
root# dnf install -y lvm2
```

## 建立 LVM

### PV 操作

```
root# lsblk
root# blkid
```

```
root# pvcreate /dev/sdb
```

```
root# lsblk
root# blkid
```

檢視 PV 狀態

```
root# pvscan

root# pvdisplay

root# pvs
```

### VG 操作

```
root# vgcreate vg_01 /dev/sdb
```

檢視 VG 狀態

```
root# vgscan

root# vgdisplay

root# vgs
```

### LV 操作

```
root# lvcreate -L 2G -n lv_01 vg_01
```

檢視 LV 狀態

```
root# lvscan

root# lvdisplay

root# lvs
```

## 掛載使用

```
root# mkfs.xfs /dev/vg_01/lv_01 
```

```
root# mkdir /data/

root# mount /dev/vg_01/lv_01 /data/
```

```
root# touch /data/lvm_f1
```

## 開機啟動

```
root# cp /etc/fstab{,_backup}
```

```
root# vi /etc/fstab
```

```=
最後一行新增
...

/dev/vg_01/lv_01 /data xfs defaults 0 0
```

> 或是 `UUID=XXXXXX-YYYYY /data xfs defaults 0 0`

```
root# umount /data
root# df -h /data/
```

```
root# mount -a
```

> 必須確認沒有出現錯誤

```
root# reboot
```

@Server

```
root# df -h /data/
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`



---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# LAB 建立第 2 個 LV

## 條件

* 從原有的 vg `vg_01` 建立新的 lv。
* lv 名為 `lab_lv01`，大小 1GB。
* 將 `lab_lv01` 掛載至 /lab/ 目錄。
* 重開機後必須自動掛載生效。
* 使用 lvs 時，可看到 `lv_01` 與 `lab_lv01`。
    ![](https://i.imgur.com/swUNzYY.png)


## Solutions

@Server

```
root# lvcreate -L 1G -n lab_lv01 vg_01
root# lvs

root# mkfs.xfs /dev/vg_01/lab_lv01 
root# blkid
```

```
root# vi /etc/fstab
```

```=
新增
...

UUID=ab7e71c8-f14b-4318-895d-e8e61bb48887 /lab xfs defaults 0 0
```

```
root# mkdir /lab

root# mount -a
```

```
root# touch /lab/labfile

root# reboot
```

```
root# df -h /data/
root# df -h /lab/
```

> ![](https://i.imgur.com/Vk1vIHg.png)

```
root# vgs
root# lvs
```

> ![](https://i.imgur.com/TOicmLr.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# LVM 空間擴展

將 `vol_01` 新增 512MB

@Server

## 檢查 Volume 相關資訊

```
root# df /data
```

```
root# lvs /dev/vg_01/lv_01
  LV    VG    Attr       LSize Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  lv_01 vg_01 -wi-ao---- 2.00g
```

```
root# lvdisplay vg_01/lv_01
  --- Logical volume ---
  LV Path                /dev/vg_01/lv_01
  LV Name                lv_01
  VG Name                vg_01
  LV UUID                aMdMYx-hETn-5Ve1-T7qW-0dKX-vCVX-5v310F
  LV Write Access        read/write
  LV Creation host, time esys-lab-lvm, 2022-07-07 14:03:58 +0800
  LV Status              available
  # open                 1
  LV Size                2.00 GiB
  Current LE             512
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     8192
  Block device           253:0
```

檢查 VG 可用空間

```
root# vgdisplay vg_01
  --- Volume group ---
  VG Name               vg_01
  System ID             
  Format                lvm2
  Metadata Areas        1
  Metadata Sequence No  2
  VG Access             read/write
  VG Status             resizable
  MAX LV                0
  Cur LV                1
  Open LV               1
  Max PV                0
  Cur PV                1
  Act PV                1
  VG Size               <20.00 GiB
  PE Size               4.00 MiB
  Total PE              5119
  Alloc PE / Size       512 / 2.00 GiB
  Free  PE / Size       4607 / <18.00 GiB
  VG UUID               ZGUVyH-z4Ku-GT4a-rRof-LJlw-R41V-ia0H5I
```

## 擴展 LV 空間

```
root# lvextend /dev/vg_01/lv_01 -L +512M
  Size of logical volume vg_01/lv_01 changed from 2.00 GiB (512 extents) to 2.50 GiB (640 extents).
  Logical volume vg_01/lv_01 successfully resized.
```

```
root# lvs
  LV    VG    Attr       LSize Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  lv_01 vg_01 -wi-ao---- 2.50g
```

```
root# lvdisplay vg_01/lv_01
  --- Logical volume ---
  LV Path                /dev/vg_01/lv_01
  LV Name                lv_01
  VG Name                vg_01
  LV UUID                aMdMYx-hETn-5Ve1-T7qW-0dKX-vCVX-5v310F
  LV Write Access        read/write
  LV Creation host, time esys-lab-lvm, 2022-07-07 14:03:58 +0800
  LV Status              available
  # open                 1
  LV Size                2.50 GiB
  Current LE             640
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     8192
  Block device           253:0
```

## 擴展 File System

```
root# lsblk /dev/vg_01/lv_01 
NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
vg_01-lv_01 253:0    0  2.5G  0 lvm  /data

root# lvs /dev/vg_01/lv_01 
  LV    VG    Attr       LSize Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  lv_01 vg_01 -wi-ao---- 2.50g
  
root# df -h /data/
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/vg_01-lv_01  2.0G   47M  2.0G   3% /data
```

```
root# xfs_growfs /data/
```

```
root# df -h /data/
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/vg_01-lv_01  2.5G   51M  2.5G   2% /data
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# LVM 快照

## 建立快照

```
root# lvcreate -s -L 50M -n sp_01 vg_01/lv_01
```

```
root# lvs
  LV     VG    Attr       LSize  Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  lv_01  vg_01 owi-aos---  2.50g                                                    
  sp_001 vg_01 swi-a-s--- 52.00m      lv_01  0.00
```

## 測試 Snapshot 滿額

```
root# cd /data/
```

```
root# dd if=/dev/zero of=f001.img bs=1M count=10
root# lvs

root# dd if=/dev/zero of=f002.img bs=1M count=10
root# lvs

root# dd if=/dev/zero of=f003.img bs=1M count=10
root# lvs

root# dd if=/dev/zero of=f004.img bs=1M count=10
root# lvs

root# dd if=/dev/zero of=f005.img bs=1M count=10
root# lvs

root# dd if=/dev/zero of=f006.img bs=1M count=10
root# lvs
```

```
root# dmesg -T | tail
[Thu Jul  7 14:44:45 2022] EXT4-fs (dm-3): unable to read superblock
[Thu Jul  7 14:44:45 2022] EXT4-fs (dm-3): unable to read superblock
[Thu Jul  7 14:45:48 2022] Buffer I/O error on dev dm-3, logical block 655344, async page read
[Thu Jul  7 14:46:07 2022] Buffer I/O error on dev dm-3, logical block 655344, async page read
[Thu Jul  7 14:50:47 2022] device-mapper: snapshots: Invalidating snapshot: Unable to allocate exception.
[Thu Jul  7 14:51:17 2022] Buffer I/O error on dev dm-3, logical block 655344, async page read
[Thu Jul  7 14:51:17 2022] EXT4-fs (dm-3): unable to read superblock
[Thu Jul  7 14:51:17 2022] EXT4-fs (dm-3): unable to read superblock
[Thu Jul  7 14:51:17 2022] EXT4-fs (dm-3): unable to read superblock
[Thu Jul  7 14:57:08 2022] device-mapper: snapshots: Invalidating snapshot: Unable to allocate exception.
```

```
root# mkdir /mnt/sp_01/

root# mount /dev/vg_01/sp_01 /mnt/sp_01/
mount: /mnt/sp_01: can't read superblock on /dev/mapper/vg_01-sp_01.
```

> Snapshot 若滿了，則會掛載失敗，OS 會自動停用該 Snapshot

移除損壞的 Snapshot

```
root# echo y | lvremove vg_01/sp_01
```

## 測試 Snapshot 還原

```
root# rm -rf /data/*

root# cd /data/

root# for f in {1..5}
> do
> dd if=/dev/zero of=file-${f}.img bs=1M count=10
> done
```

建立新的 Snapshot (`sp_001`)

```
root# lvcreate -s -L 50M -n sp_001 vg_01/lv_01

root# lvs
```

```
root# rm -rf /data/*
```

將 `sp_001` 掛載至 `/mnt/sp_001/`

```
root# mkdir -p /mnt/sp_001/

root# mount -o nouuid /dev/vg_01/sp_001 /mnt/sp_001/

root# df -h
```

```
root# ls -lh /mnt/sp_001/
```

將 `/mnt/sp_001/` 還原至 `/backup/`

```
root# mkdir /backup/

root# rsync -av /mnt/sp_001/ /backup/
FAIL! (command not found)

root# dnf install -y rsync

root# rsync -av /mnt/sp_001/ /backup/
```

## 移除快照

```
root# umount /mnt/sp_001/ 

root# lvs

root# lvremove vg_01/sp_001
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 清除作業

```
root# cat /etc/fstab_backup > /etc/fstab

root# umount /data
root# umount /lab

root# mount -a
root# df -h
```

> 不可出現有 LVM 的掛載

```
root# for v in $(ls /dev/vg_01/); do echo y | lvremove /dev/vg_01/${v}; done

root# vgremove vg_01

root# pvremove /dev/sdb
```

```
root# rm -rf /mnt/*
root# rm -rf /data/
```

```
root# lsblk
root# blkid
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# LVM LAB

## 事件流程

1. 建立一 VG 為 `lab_vg_01`
2. 從 `lab_vg_01` 中新增 LV `lv_01`，大小 200MB，格式化為 `xfs`
3. 設定 `lv_01` 開機自動掛載到 `/data/`
4. 在 `/data/` 新增 4 檔案

    ```
    root# dd if=/dev/zero of=f-01.img bs=1M count=10
    root# dd if=/dev/zero of=f-02.img bs=1M count=20
    root# dd if=/dev/zero of=f-03.img bs=1M count=30
    root# dd if=/dev/zero of=f-04.img bs=1M count=40
    ```
    
5. 設定 `lv_01` 之快照為 `sp_001`
6. 刪除如下檔案

    * /data/f-01.img
    * /data/f-02.img
    * /data/f-03.img

7. 將 `sp_001` 掛載至 `/sp/001/`
8. 從 `/sp/001/` 將 `f-02.img` 複至到 `/restore/`

## 檢驗

1. /data/ 中只會有下列檔案

    * f-04.img

2. /sp/001/ 中會有下列檔案

    * f-01.img
    * f-02.img
    * f-03.img
    * f-04.img

3. /restore/ 中會有下列檔案

    * f-02.img

![](https://i.imgur.com/Y6xCAJO.png)


## Solutions

```
root# dd if=/dev/zero of=/dev/sdb bs=1M count=10
```

```
root# pvcreate /dev/sdb
root# vgcreate lab_vg_01 /dev/sdb
root# lvcreate -L 200M -n lab_vg_01 lab_vg_01
```

```
root# mkfs.xfs /dev/lab_vg_01/lab_vg_01 

root# mkdir /data
```

```
root# blkid /dev/lab_vg_01/lab_vg_01 

root# echo UUID=b5863d65-b752-42a6-b9f8-4480b46bc354 /data xfs defaults 0 0 >> /etc/fstab
root# mount -a
root# df -h
```

```
root# cd /data/
root# dd if=/dev/zero of=f-01.img bs=1M count=10
root# dd if=/dev/zero of=f-02.img bs=1M count=20
root# dd if=/dev/zero of=f-03.img bs=1M count=30
root# dd if=/dev/zero of=f-04.img bs=1M count=40
```

```
root# lvcreate -s -L 100M -n sp_001 /dev/lab_vg_01/lab_vg_01 

root# rm -f /data/f-01.img /data/f-02.img /data/f-03.img
```

```
root# mkdir -p /sp/001

root# mount -o ro /dev/lab_vg_01/sp_001 /sp/001/
FAIL!
root# mount -o ro,nouuid /dev/lab_vg_01/sp_001 /sp/001/

root# cd /sp/001/
```

```
root# mkdir /restore
root# cp f-02.img /restore/
```

```
root# ls /data/
root# ls /sp/001/
root# ls /restore/
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Podman 安裝

@Server

## 校時

參考 https://hackmd.io/@esys/B1kBWK_q9/%2FNDpWNIEgQlWFIzD5GJIsYg

## 安裝 Podman

```
root# podman images
-bash: podman: command not found
```

```
root# dnf install -y podman
```

```
root# podman images
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Container Image Pull

@Server

```
root# podman images
```

```
root# podman pull almalinux
? Please select an image: 
    registry.fedoraproject.org/almalinux:latest
    registry.access.redhat.com/almalinux:latest
    registry.centos.org/almalinux:latest
  ▸ docker.io/library/almalinux:latest
```

> 使用上下鍵選擇 `docker.io`

![](https://i.imgur.com/oKWLzgF.png)

```
root# podman images
```

![](https://i.imgur.com/cnRhniK.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`

---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 建立 Container

![](https://i.imgur.com/pIJWSZB.png)


## 啟用 Container

```
root# podman images

root# podman ps

root# podman ps -a
```

```
root# podman run --name alma1 almalinux:latest
```

```
root# podman ps -a
```

```
root# podman rm alma1

root# podman ps -a
```

![](https://i.imgur.com/CNnU8NS.png)

## Container 加入互動

@Server

```
root# podman rm alma1
```

```
root# podman run -it --name alma1 almalinux:latest
root@ContainerID# 
```

![](https://i.imgur.com/vKX9p9v.png)

```
root@ContainerID# top
root@ContainerID# ls
root@ContainerID# exit
```

```
root# podman ps
root# podman ps -a
```

## 建立 web 服務

@Desktop

Firefox: http://172.16.170.1X:8081
FAIL!

@Server

```
root# podman run -it --name web1 -p 8081:80 almalinux:latest
```




```
root@ContainerID# dnf install -y httpd

root@ContainerID# httpd
```

@Server

```
root# podman inspect web1

root# podman inspect web | grep IPAdd
```

@Desktop

Firefox: http://172.16.170.1X:8081
![](https://i.imgur.com/6yoF0MG.png)

@Server

```
root@ContainerID# exit
```

@Desktop

Firefox: http://172.16.170.1X:8081
FAIL!

@Server

```
root# podman ps -a

root# podman start web1

root# podman exec -it web1 bash

root@ContainerID# exit

root# 
```

@Desktop

Firefox: http://172.16.170.1X:8081
FAIL!

@Server

```
root# podman exec web1 httpd
```

@Desktop

Firefox: http://172.16.170.1X:8081
![](https://i.imgur.com/6yoF0MG.png)

@Server

```
root# podman stop web1 

root# podman rm web1
```

## 補充: 

### Container 內部安裝行程管理套件

```
root@ContainerID# top
FAIL!

root@ContainerID# dnf provides '*bin/top'
root@ContainerID# dnf install procps-ng

root@ContainerID# top
```

### 在進入 Container 執行程式

```
root# podman exec -it web1 bash
root@ContainerID# ps aux

root@ContainerID# httpd

root@ContainerID# ps aux

root@ContainerID# exit

root# 
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Container 掛載目錄

![](https://i.imgur.com/rkrdvqz.png)


Terminal 1

@Server

```
root# mkdir -p /data/web
```

```
root# podman run -it --name web1 -p 8081:80 -v /data/web:/var/www/html:Z almalinux:latest

root@ContainerID# dnf install -y httpd
root@ContainerID# httpd
```

Terminal 2

```
root# echo "Hello" > /data/web/index.html
```

@Desktop

Firefox: http://172.16.170.1X:8081/

![](https://i.imgur.com/fQ4z0y9.png)



###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 多容器掛載同一目錄

## 保持啟動 web1

@Server

```
root# podman ps -a

root# podman start web1
root# podman exec web1 httpd
```

@Desktop

Firefox: http://172.16.170.1X:8081

![](https://i.imgur.com/EZo7Xhf.png)

## 啟動 web2

@Server

```
root# podman run -it --name web2 -p 8082:80 -v /data/web:/var/www/html:Z almalinux:latest

root@ContainerID# dnf install -y httpd
root@ContainerID# httpd
```

@Desktop

Firefox: http://172.16.170.1X:8082

![](https://i.imgur.com/YMEx83O.png)

@Server

```
root# echo "Hello Page" > /data/web/page.html
```

@Desktop
Firefox: http://172.16.170.1X:8081/page.html
FAIL!

Firefox: http://172.16.170.1X:8082/page.html


## 使用 Podman volume 管理掛載

```
root# podman stop web1
root# podman stop web2

root# podman rm web1
root# podman rm web2
```

```
root# podman volume create web
root# podman inspect web
[
    {
        "Name": "web",
        "Driver": "local",
        "Mountpoint": "/var/lib/containers/storage/volumes/web/_data",
        "CreatedAt": "2022-07-29T22:56:16.829857648+08:00",
        "Labels": {},
        "Scope": "local",
        "Options": {}
    }
]
```

```
root# podman run -it --name web1 -p 8081:80 -v web:/var/www/html almalinux:latest
root@ContainerID# dnf install -y httpd
root@ContainerID# exit

root# podman run -it --name web2 -p 8082:80 -v web:/var/www/html almalinux:latest
root@ContainerID# dnf install -y httpd
root@ContainerID# exit

root# podman start web1
root# podman start web2

root# podman exec web1 httpd
root# podman exec web2 httpd
```

```
root# echo Hello > /var/lib/containers/storage/volumes/web/_data/index.html
root# echo Page > /var/lib/containers/storage/volumes/web/_data/page.html
```

@Desktop

Firefox: http://172.16.170.1X:8081/, http://172.16.170.1X:8081/page.html

![](https://i.imgur.com/kthFzhf.png)

![](https://i.imgur.com/UnfSYB3.png)

Firefox: http://172.16.170.1X:8082/, http://172.16.170.1X:8082/page.html

![](https://i.imgur.com/FsFREPi.png)

![](https://i.imgur.com/iT9WblC.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 修正 Container 目錄同時掛載

@Server

```
root# podman stop web1
root# podman stop web2

root# podman rm web1
root# podman rm web2
```

```
root# podman volume list

root# podman volume remove web

root# podman volume list
```

> 刪除 Volume

```
root# rm -rf /data/

root# mkdir -p /data/web/

root# ls -lZ /data/
root# chcon -R -t container_file_t /data/web/
root# ls -lZ /data/
```

```
root# podman run -it --name web1 -p 8081:80 -v /data/web:/var/www/html almalinux:latest
root@ContainerID# dnf install -y httpd
root@ContainerID# exit

root# podman run -it --name web2 -p 8082:80 -v /data/web:/var/www/html almalinux:latest
root@ContainerID# dnf install -y httpd
root@ContainerID# exit

root# podman start web1
root# podman start web2

root# podman exec web1 httpd
root# podman exec web2 httpd
```

```
root# cd /data/web/
```

```
root# echo Hello > index.html
root# echo Page > page.html
```

@Desktop

Firefox: http://172.16.170.1X:8081/, http://172.16.170.1X:8081/page.html
Firefox: http://172.16.170.1X:8082/, http://172.16.170.1X:8082/page.html

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 建立 web Image

@Server

```
root# cd

root# mkdir web-server; cd web-server
```

```
root# vi Dockerfile
```

```=
from almalinux:latest

RUN dnf install -y httpd procps-ng && dnf clean all

ENTRYPOINT ["/usr/sbin/httpd", "-DFOREGROUND"]

VOLUME ["/var/www/html/"]

EXPOSE 80
```

```
root# podman images

root# podman build -t web-server:1 ./

root# podman images
```

```
root# podman inspect web-server | grep -A 5 Volumes
            "Volumes": {
                "/var/www/html/": {}
            },
            "Labels": {
                "io.buildah.version": "1.22.3"
            }
```

![](https://i.imgur.com/eI70DHR.png)

## 使用自建 Image

@Server

```
root# podman stop web1
root# podman stop web2
root# podman rm web1
root# podman rm web2
```

```
root# podman run -itd --name web1 -p 8081:80 -v /data/web:/var/www/html web-server:1
root# podman run -itd --name web2 -p 8082:80 -v /data/web:/var/www/html web-server:1
```

@Desktop

Firefox: http://172.16.170.1X:8081/, http://172.16.170.1X:8081/page.html
Firefox: http://172.16.170.1X:8082/, http://172.16.170.1X:8082/page.html

@Server

```
root# podman exec web1 ps aux
root# podman exec web2 ps aux
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`

---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Container Save/Load

@Server

```
root# cd
root# cd web-server/
root# podman save web-server:1 > web-server_1.tar

root# ls -lh
```

@Desktop

```
root# cd

root# scp root@172.16.170.1X:/root/web-server/web-server_1.tar ./
```

```
root# podman images

root# podman load < web-server_1.tar 

root# podman images
```

```
root# mkdir -p /data/web

root# podman run -itd --name web2 -p 8082:80 -v /data/web:/var/www/html web-server:1
root# podman run -itd --name web1 -p 8081:80 -v /data/web:/var/www/html web-server:1

root# podman ps
```

```
root# cd /data/web/
root# ls -lh
root# echo Hello Hello > index.html
```

Firefox: http://172.16.170.X:8081/index.html
FAIL!

Firefox: http://172.16.170.X:8082/index.html
FAIL!

```
root# ls -lZ /data/web/
root# chcon -R -t container_file_t /data/web/

root# ls -lZ /data/web/
```

Firefox: http://172.16.170.X:8081/index.html
Firefox: http://172.16.170.X:8082/index.html

![](https://i.imgur.com/oICxQIl.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`

---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# NFS Server

@Desktop

```
root# dnf install -y nfs-utils
```

```
root# mkdir -p /nfs-data/web

root# echo "/nfs-data/web 172.16.170.0/24(rw)" >> /etc/exports

root# systemctl enable --now nfs-server

root# firewall-cmd --permanent --add-service=nfs
root# firewall-cmd --reload
```

```
root# showmount -e localhost
```

@Server

```
root# dnf install -y nfs-utils
```

測試掛載

```
root# df -h /mnt

root# mount -t nfs 172.16.170.X:/nfs-data/web /mnt

root# df -h /mnt

root# umount /mnt
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Shell 單引號/雙引號差別

![](https://i.imgur.com/6Sdzb1G.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# OS 掛載 NFS

@Desktop, @Server

```
root# podman stop web1
root# podman stop web2
```

@Desktop

```
root# echo hello from nfs > /nfs-data/web/index.html
```

## 掛載 Volume

@Server, @Desktop

```
root# mkdir -p /data/web/
```

```
root# mount -t nfs 172.16.170.X:/nfs-data/web /data/web

root# df -h /data/web/
```

## 啟動 web1

@Server, @Desktop

```
root# podman start web1
root# podman start web2
```

# 測試

@Desktop

```
root# # curl http://172.16.170.X:8081/index.html 
hello from nfs
root# # curl http://172.16.170.1X:8081/index.html 
hello from nfs

root# # curl http://172.16.170.X:8082/index.html 
hello from nfs
root# # curl http://172.16.170.1X:8082/index.html 
hello from nfs
```

## 清除掛載

@Server, @Desktop

```
root# podman stop web1
root# podman stop web2

root# podman rm web1
root# podman rm web2
```

```
root# umount /data/web

root# df -h /data/web
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Podman 管理 NFS

@Server, @Desktop

```
root# podman volume create \
--opt type=nfs4 \
--opt o=rw \
--opt device=172.16.170.X:/nfs-data/web web
```

```
root# podman volume inspect web
```

```
root# # podman volume inspect web
[
    {
        "Name": "web",
        "Driver": "local",
        "Mountpoint": "/var/lib/containers/storage/volumes/web/_data",
        "CreatedAt": "2022-07-30T00:27:41.669925133+08:00",
        "Labels": {},
        "Scope": "local",
        "Options": {
            "device": "172.16.170.X:/data/web",
            "o": "rw"
        }
    }
]

```

## 啟動 Web1, Web2

@Server, @Desktop

```
root# podman run -itd --name web1 -v web:/var/www/html/ -p 8081:80 web-server:1
root# podman run -itd --name web2 -v web:/var/www/html/ -p 8082:80 web-server:1
```

@Desktop

```
root# curl http://172.16.170.1X:8081/index.html 
hello from nfs

root# curl http://172.16.170.1X:8082/index.html 
hello from nfs

root# curl http://172.16.170.X:8081/index.html 
hello from nfs

root# curl http://172.16.170.X:8082/index.html 
hello from nfs
```


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# NFS 掛載測試寫入

@Server

```
root# podman stop web1
root# podman stop web2
root# podman rm web1
root# podman rm web2
```

```
root# cd web-server
```

```
root# vi Dockerfile
```

```=
from almalinux:latest

RUN dnf install -y httpd php-fpm && dnf clean all

COPY run.sh /usr/local/bin/

ENTRYPOINT ["/usr/local/bin/run.sh"]

VOLUME ["/var/www/html/"]

EXPOSE 80
```

```
root# vi run.sh
```

```=
#!/bin/bash

LANG=C

mkdir /run/php-fpm

php-fpm
/usr/sbin/httpd -DFOREGROUND
```

```
root# chmod +x run.sh
```

```
root# podman build -t web-server:2 ./
root# podman images

root# podman run -itd --name web1 -v web:/var/www/html/ -p 8081:80 web-server:2
root# podman run -itd --name web2 -v web:/var/www/html/ -p 8082:80 web-server:2
```

@Desktop

```
root# cd /nfs-data/web/
```

```
root# vi write.php
```

```php=
<?php file_put_contents("log.txt", "test message\n", FILE_APPEND); ?>
```

```
root# curl http://172.16.170.1X:8081/write.php
root# curl http://172.16.170.1X:8082/write.php
```

```
root# ls -lh /nfs-data/web/log.txt
FAIL!
```

```
root# vi /etc/exports
```

```=
/nfs-data/web 172.16.170.0/24(rw,all_squash)
```

```
root# systemctl reload nfs-server

root# chown -R nobody /nfs-data/web/
```

```
root# curl http://172.16.170.1X:8081/write.php
root# curl http://172.16.170.1X:8082/write.php
```

```
root# cat /nfs-data/web/log.txt
test message
test message
test message
test message
test message
```


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Apache Virtualhost

* 建立 `web1.linux.class`
* 建立 `web2.linux.class`

@Server

```
root# dnf list httpd
root# dnf install -y httpd
root# dnf list httpd
```

```

root# cd /etc/httpd/conf.d/
root# ls
root# cp /usr/share/doc/httpd/httpd-vhosts.conf ./web1.linux.class.conf
root# ls -lh
```

```
root# vi web1.linux.class.conf 
```

```=
<VirtualHost *:80>
    ServerAdmin webmaster@web1.linux.class
    DocumentRoot "/var/www/html/web1.linux.class"
    ServerName web1.linux.class
    ErrorLog "/var/log/httpd/web1.linux.class-error_log"
    CustomLog "/var/log/httpd/web1.linux.class-access_log" common
</VirtualHost>
```

```
root# cp web1.linux.class.conf web2.linux.class.conf
```

```
root# vi web2.linux.class.conf 
```

```=
<VirtualHost *:80>
    ServerAdmin webmaster@web2.linux.class
    DocumentRoot "/var/www/html/web2.linux.class"
    ServerName web2.linux.class
    ErrorLog "/var/log/httpd/web2.linux.class-error_log"
    CustomLog "/var/log/httpd/web2.linux.class-access_log" common
</VirtualHost>
```

```
root# cd /var/www/html/
root# ls -lh

root# mkdir {web1,web2}.linux.class
root# ls -lh
```

```
root# echo web1 > web1.linux.class/index.html
root# echo web2 > web2.linux.class/index.html
```

```
root# firewall-cmd --permanent --add-service=http
root# firewall-cmd --reload

root# systemctl restart httpd
root# systemctl status httpd
```

@Desktop

```
root# cp -a /etc/hosts /etc/hosts_backup
```

```
root# echo 172.16.170.1X web1.linux.class >> /etc/hosts
root# echo 172.16.170.1X web2.linux.class >> /etc/hosts
```

```
root# curl web1.linux.class
root# curl web2.linux.class
```

![](https://i.imgur.com/k1zF3mV.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Nginx Virtualhost

@Server

```
root# dnf list nginx
root# dnf install -y nginx
root# systemctl stop httpd
```

```
root# cd /etc/nginx/conf.d/
root# pwd
root# ls
```

```
root# vi web1.linux.class.conf
```

```=
server {
    listen 80;
    server_name web1.linux.class;

    index index.html index.php index.htm;

    root /var/www/html/web1.linux.class;
}
```

```
root# cp web1.linux.class.conf web2.linux.class.conf 
```

```
root# vi web2.linux.class.conf 
```

```=
server {
    listen 80;
    server_name web2.linux.class;

    index index.html index.php index.htm;

    root /var/www/html/web2.linux.class;
}
```

```
root# nginx -t

root# systemctl start nginx
```

@Desktop

```
root# curl http://web1.linux.class
root# curl http://web2.linux.class

root# curl -I http://web1.linux.class
root# curl -I http://web2.linux.class
```

![](https://i.imgur.com/cTCwk8R.png)

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Apache 安裝憑證 + 自簽憑證

@Server

```
root# mkdir /etc/httpd/conf/ssl/
root# cd /etc/httpd/conf/ssl/
```

建立 web1 自簽憑證

```
root# openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout web1-self.key -out web1-self.crt

Generating a RSA private key
............................................................................................................+++++
................+++++
writing new private key to 'web1-self.key'
-----
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [XX]:TW (國藉)
State or Province Name (full name) []:Taipei (行政區)
Locality Name (eg, city) [Default City]:New Taipei City (縣市)
Organization Name (eg, company) [Default Company Ltd]:LinuxClass (公司名)
Organizational Unit Name (eg, section) []:IT (部門)
Common Name (eg, your name or your server's hostname) []:web1.linux.class (網址 **不能錯**)
Email Address []:
```

查看 web1 自簽憑證內容

```
root# cat web1-self.crt 
root# cat web1-self.key

root# openssl x509 -in web1-self.crt -text
```

建立 web2 自簽憑證

```
root# openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout web2-self.key -out web2-self.crt
```

安裝 Apache SSL 模組

```
root# dnf list mod_ssl
root# dnf install mod_ssl
```

設定 web1 SSL 功能

```
root# cd /etc/httpd/conf.d/
```

```
root# vi web1.linux.class.conf 
```

```=
<VirtualHost *:80>
    ServerAdmin webmaster@web1.linux.class
    DocumentRoot "/var/www/html/web1.linux.class"
    ServerName web1.linux.class
    ErrorLog "/var/log/httpd/web1.linux.class-error_log"
    CustomLog "/var/log/httpd/web1.linux.class-access_log" common
</VirtualHost>

<VirtualHost _default_:443>

    DocumentRoot "/var/www/html/web1.linux.class"
    ServerName web1.linux.class
    ErrorLog "/var/log/httpd/https_web1.linux.class-error_log"
    CustomLog "/var/log/httpd/https_web1.linux.class-access_log" common

    SSLEngine on
    SSLCertificateFile /etc/httpd/conf/ssl/web1-self.crt
    SSLCertificateKeyFile /etc/httpd/conf/ssl/web1-self.key

</VirtualHost>
```

設定 web2 SSL 功能

```
root# vi web2.linux.class.conf 
```

```=
<VirtualHost *:80>
    ServerAdmin webmaster@web2.linux.class
    DocumentRoot "/var/www/html/web2.linux.class"
    ServerName web2.linux.class
    ErrorLog "/var/log/httpd/web2.linux.class-error_log"
    CustomLog "/var/log/httpd/web2.linux.class-access_log" common
</VirtualHost>

<VirtualHost _default_:443>

    DocumentRoot "/var/www/html/web2.linux.class"
    ServerName web2.linux.class
    ErrorLog "/var/log/httpd/https_web2.linux.class-error_log"
    CustomLog "/var/log/httpd/https_web2.linux.class-access_log" common

    SSLEngine on
    SSLCertificateFile /etc/httpd/conf/ssl/web2-self.crt
    SSLCertificateKeyFile /etc/httpd/conf/ssl/web2-self.key

</VirtualHost>
```

啟動服務與防火牆

```
root# systemctl stop nginx
root# systemctl restart httpd

root# firewall-cmd --permanent --add-service=https
root# firewall-cmd --reload
```

@Desktop

```
root# curl https://web1.linux.class
FAIL!
root# curl -k https://web1.linux.class

root# curl https://web2.linux.class
FAIL!
root# curl -k https://web2.linux.class
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`

---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Apache 安裝簽證憑證

```
root# cd /etc/httpd/conf/ssl
```

## 建立憑證請求檔 (CSR)

@Server

```
root# cd /etc/httpd/conf/ssl/
```

```
root# openssl req -new -newkey rsa:2048 \
> -nodes -out web1.linux.class.csr \
> -keyout web1.linux.class.key 
```

```
root# ls -lh web1.linux.class.*

root# cat web1.linux.class.csr
```

```=
等待發證
```

```
root# cd /etc/httpd/conf/ssl/

root# curl -OJL  http://172.16.60.253/alma8/c171_inet/ca/certs/X/web1.linux.class.crt
```

```
root# openssl rsa -noout -modulus -in web1.linux.class.key | openssl md5
root# openssl x509 -noout -modulus -in web1.linux.class.crt | openssl md5
```

## 安裝憑證 (CRT, KEY)

```
root# cd /etc/httpd/conf.d/
```

```
root# vi web1.linux.class.conf
```

```=
<VirtualHost *:80>
    ServerAdmin webmaster@web1.linux.class
    DocumentRoot "/var/www/html/web1.linux.class"
    ServerName web1.linux.class
    ErrorLog "/var/log/httpd/web1.linux.class-error_log"
    CustomLog "/var/log/httpd/web1.linux.class-access_log" common
</VirtualHost>

<VirtualHost _default_:443>

    DocumentRoot "/var/www/html/web1.linux.class"
    ServerName web1.linux.class
    ErrorLog "/var/log/httpd/https_web1.linux.class-error_log"
    CustomLog "/var/log/httpd/https_web1.linux.class-access_log" common

    SSLEngine on
    # 修改為新的憑證 crt
    SSLCertificateFile /etc/httpd/conf/ssl/web1.linux.class.crt
    # 修改為新的憑證 key
    SSLCertificateKeyFile /etc/httpd/conf/ssl/web1.linux.class.key

</VirtualHost>
```

```
root# systemctl restart httpd
```

@Desktop

```
root# curl https://web1.linux.class
web1

root# curl https://web2.linux.class
FAIL!
```

Firefox: https://web1.linux.class

## 補充

### 新增 ca 檔到系統

```
root# cd /etc/pki/ca-trust/source/anchors/
root# curl http://172.16.60.253/alma8/c171_inet/ca/ca.crt > linuxclass-ca.crt

root# update-ca-trust 
```

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Nginx 反向代理

![](https://i.imgur.com/vwzjPrk.png)

@Server

```
root# dnf remove httpd 
root# dnf remove nginx
```

```
root# rm -rf /etc/nginx/

root# firewall-cmd --permanent --remove-service=http
root# firewall-cmd --permanent --remove-service=https
root# firewall-cmd --reload
```

```
root# dnf install podman

root# mkdir ~/lab-web
root# cd ~/lab-web/
```

```
root# podman images

root# curl -OJL http://172.16.60.253/alma8/c171_inet/container/lab-web/lab-web_1.tar.gz
root# gunzip lab-web_1.tar.gz 

root# podman load <lab-web_1.tar 
root# podman images
```

```
root# podman run -itd --name lab1 -p 8081:80 lab-web:1
root# podman ps
root# podman exec -it lab1 bash
```

@Desktop

```
root# cat /etc/hosts_backup > /etc/hosts

root# echo 172.16.170.X lab.linux.class >> /etc/hosts

root# curl http://lab.linux.class
```

```
root# dnf install -y nginx
```

```
root# cd /etc/nginx/conf.d/
```

```
root# vi lab.linux.class.conf
```

```=
server {
    listen 80;
    server_name lab.linux.class;

    location / {
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header Port $server_port;
        proxy_set_header Schema $scheme;
        proxy_set_header URI $uri;

        proxy_pass http://lab.linux.class;

    }
}
```

```
root# vi 0_upstream.conf
```

```=
upstream lab.linux.class {

    server 172.16.170.1X:8081;
}
```

```
root# nginx -t
root# systemctl start nginx
```

```
root# curl http://lab.linux.class
FAIL!
```

```
root# ausearch -m avc
root# getsebool -a | grep http | grep connect
root# setsebool -P httpd_can_network_connect on
root# getsebool -a | grep http | grep connect
```

```
root# curl http://lab.linux.class
```

@Server

```
root# podman exec -it lab1 bash
root@ContainerID# echo Hello Container > /var/www/html/index.html
root@ContainerID# exit

root#
```

@Desktop

```
root# curl http://lab.linux.class
```

![](https://i.imgur.com/6N73KMT.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Nginx NLB

@Server

```
root# podman run -itd --name lab2 -p 8082:80 lab-web:1
```

```
root# podman exec -it lab1 bash
root@ContainerID# echo lab1 > /var/www/html/index.html 
root@ContainerID# exit

root# podman exec -it lab2 bash
root@ContainerID# echo lab2 > /var/www/html/index.html
root@ContainerID# exit
```

@Desktop

```
root# vi /etc/nginx/conf.d/0_upstream.conf
```

```=
upstream lab.linux.class {

    server 172.16.170.1X:8081;
    server 172.16.170.1X:8082;
}
```

```
root# nginx -t
root# systemctl reload nginx
```

```
root# curl lab.linux.class
web1
root# curl lab.linux.class
web2
```

![](https://i.imgur.com/jukmaw2.png)

## ip_hash

```
root# vi /etc/nginx/conf.d/0_upstream.conf
```

```=
upstream lab.linux.class {
    ip_hash;

    server 172.16.170.1X:8081;
    server 172.16.170.1X:8082;
}
```

```
root# nginx -t
root# systemctl reload nginx
```

Firefox: http://lab.linux.class

###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Ngninx NLB SSL

![](https://i.imgur.com/Tui3cxi.png)


@Server

```
root# podman stop lab1
root# podman stop lab2

root# podman rm lab1
root# podman rm lab2
```

```
root# podman run -itd --name lab1 -p 8081:80 lab-web:1
root# podman run -itd --name lab2 -p 8082:80 lab-web:1
```

```
root# podman exec -it lab1 bash
root@ContainerID# echo lab1 > /var/www/html/index.html 
root@ContainerID# exit

root# podman exec -it lab2 bash
root@ContainerID# echo lab2 > /var/www/html/index.html
root@ContainerID# exit
```

@Desktop

```
root# vi /etc/nginx/conf.d/0_upstream.conf
```

```=
upstream lab.linux.class {
    server 172.16.170.1X:8081;
    server 172.16.170.1X:8082;
}
```

```
root# vi /etc/nginx/conf.d/lab.linux.class.conf
```

```=
server {
    listen 80;
    server_name lab.linux.class;

    location / {
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header Port $server_port;
        proxy_set_header Schema $scheme;
        proxy_set_header URI $uri;

        proxy_pass http://lab.linux.class;

    }
}

server {
    listen 443 ssl http2;
    server_name lab.linux.class;

    ssl_certificate        /etc/nginx/ssl/lab.linux.class.crt;
    ssl_certificate_key    /etc/nginx/ssl/lab.linux.class.key;

    location / {
        proxy_set_header X-Real-IP  $remote_addr;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header Port $server_port;
        proxy_set_header Schema $scheme;
        proxy_set_header URI $uri;

        proxy_pass http://lab.linux.class;

    }
}

```

```
root# mkdir /etc/nginx/ssl/

root# cd /etc/nginx/ssl/
```

```
root# curl -OJL http://172.16.60.253/alma8/c171_inet/ca/certs/lab.linux.class/lab.linux.class.crt
root# curl -OJL http://172.16.60.253/alma8/c171_inet/ca/certs/lab.linux.class/lab.linux.class.key
```

```
root# nginx -t

root# systemctl reload nginx

root# curl https://lab.linux.class
```

Firefox: https://lab.linux.class

![](https://i.imgur.com/d6qPRPr.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# LAB - Nginx NLB/SSL

## 架構

![](https://i.imgur.com/W0UbLmF.png)

## 需求說明

* 在 Server 中，載入 `lab-web_1.tar` 之容器 Image，名應為 `lab-web:1`
* 從 lab-web: 1 中執行容器 `web1` 與 `web2`，規格如下：
    * Web1: Port `8081:80`
    * Web2: Port `8082:80`
    * Web1, Web2: 從 NFS 掛載 至 `/var/www/html/`
    * 掛載來源: `172.16.170.X:/web (rw)`
* 在 Desktop 中，設定 NFS 分享，規格如下：
    * 允許 Server (`172.16.170.1X`) 可對 `/web` 進行`讀寫`
    * 在 Desktop 中，使用 Nginx 設定 `lab.linux.class` 之反向代理，規格如下：
    * Upstream 為 Server 中的 `web1` 與 `web2`，使用 RR 機制。
    * 使用者使用瀏覽器開啟時，必須支援 `https`（https://lab.linux.class）


## 清空作業

@Server

```
root# podman stop lab1
root# podman stop lab2

root# podman rm lab1
root# podman rm lab2

root# podman rmi lab-web:1

root# rm -rf ~/*

root# dnf remove httpd nginx
root# rm -rf /etc/{httpd,nginx}

root# firewall-cmd --permanent --remove-service=http
root# firewall-cmd --permanent --remove-service=https
root# firewall-cmd --reload
```

@Desktop

```
root# rm -rf ~/*

root# dnf remove httpd nginx
root# rm -rf /etc/{httpd,nginx}

root# firewall-cmd --permanent --remove-service=http
root# firewall-cmd --permanent --remove-service=https
root# firewall-cmd --reload
```

## Solutions

### 設定 NFS 服務

@Desktop

```
root# dnf install -y nfs-utils
```

```
root# mkdir /web/
root# chown -R nobody:nobody /web
root# chmod 777 /web

root# echo "/web 172.16.170.1X(rw,all_squash)" > /etc/exports
root# systemctl enable --now nfs-server

root# firewall-cmd --permanent --add-service=nfs
root# firewall-cmd --reload
```

### 設定 Container

@Server

```
root# dnf install -y podman nfs-utils
```

```
root# for v in $(podman volume list | awk '{print $2}'); do podman volume rm ${v}; done
```

```
root# podman volume create --opt type=nfs4 --opt o=rw --opt device=172.16.170.X:/web web
```

```
root# mkdir lab-web; cd lab-web
root# curl -OJL http://172.16.60.253/alma8/c171_inet/container/lab-web/lab-web_1.tar.gz

root# gunzip lab-web_1.tar.gz
root# ls -lh
```

```
root# podman images
root# podman load < lab-web_1.tar 
root# podman images
```

```
root# podman run -itd --name web1 -p 8081:80 -v web:/var/www/html/ lab-web:1
root# podman run -itd --name web2 -p 8082:80 -v web:/var/www/html/ lab-web:1
```

### 設定 Reverse Proxy

@Desktop

```
root# dnf install -y nginx
```

```
root# vi /etc/nginx/conf.d/0_upstream.conf
```

```=
upstream lab.linux.class {
    server 172.16.170.1X:8081;
    server 172.16.170.1X:8082;
}
```

```
root# vi /etc/nginx/conf.d/lab.linux.class.conf
```

```=
server {
    listen 443 ssl http2;
    server_name lab.linux.class;

    ssl_certificate        /etc/nginx/ssl/lab.linux.class.crt;
    ssl_certificate_key    /etc/nginx/ssl/lab.linux.class.key;

    location / {
        proxy_set_header X-Real-IP  $remote_addr;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header Port $server_port;
        proxy_set_header Schema $scheme;
        proxy_set_header URI $uri;
        proxy_pass http://lab.linux.class;
    }
}
```

```
root# cd /web/

root# echo Hello Lab > index.html
root# echo '<?php phpinfo(); ?>' > phpinfo.php;
```

設定 SSL

```
root# mkdir /etc/nginx/ssl/; cd /etc/nginx/ssl/
```

```
root# curl -OJL http://172.16.60.253/alma8/c171_inet/ca/certs/lab.linux.class/lab.linux.class.crt
root# curl -OJL http://172.16.60.253/alma8/c171_inet/ca/certs/lab.linux.class/lab.linux.class.key
```

```
root# openssl rsa -noout -modulus -in lab.linux.class.key | openssl md5
root# openssl x509 -noout -modulus -in lab.linux.class.crt | openssl md5
```

```
root# firewall-cmd --permanent --add-service=http
root# firewall-cmd --permanent --add-service=https
root# firewall-cmd --reload
```

檢查 nginx 設定檔案是否正確

```
root# nginx -t

root# setsebool -P httpd_can_network_connect on

root# systemctl restart nginx
```

## 驗證

@Desktop

```
root# echo "172.16.170.X lab.linux.class" >> /etc/hosts
```

Firefox: https://lab.linux.class/

Firefox: https://lab.linux.class/phpinfo.php

![](https://i.imgur.com/93cETH3.png)


###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Nginx 限制流量

* http 限制 500K
* https 不限制

@Desktop

```
root# cd /etc/nginx/conf.d/
```

```
root# vi lab.linux.class.conf
```

```=
server {
    listen 80;
    server_name lab.linux.class;


    location / {
        limit_rate 500k;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header Port $server_port;
        proxy_set_header Schema $scheme;
        proxy_set_header URI $uri;

        proxy_pass http://lab.linux.class;

    }
}

server {
    listen 443 ssl http2;
    server_name lab.linux.class;

    ssl_certificate        /etc/nginx/ssl/lab.linux.class.crt;
    ssl_certificate_key    /etc/nginx/ssl/lab.linux.class.key;

    location / {
        proxy_set_header X-Real-IP  $remote_addr;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header Port $server_port;
        proxy_set_header Schema $scheme;
        proxy_set_header URI $uri;

        proxy_pass http://lab.linux.class;

    }
}
```

```
root# systemctl restart nginx
```

```
root# cd /web/
root# dd if=/dev/zero of=test.img bs=1M count=200
```

```
root# cd
root# curl -OJL http://lab.linux.class/test.img

root# curl -OJL https://lab.linux.class/test.img
```



###### tags: `全國勞工聯合總工會` `全勞聯_Linux-Integration-02`













































=============================


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---


- [rreevr](/q-gs6a5dRBGAgDbkwQtbKA)

# 7/10
Linux

AlmaLinux 

連到遠端 IP 
安裝在遠端
老師給了兩個 IP 一個裝 USER 一個裝 server
連 USER IP 安裝 server
安裝使用 kick

用 vi 改 kick 腳本

加入 kick 網路校時 功能
^^^^^^^^^^^^^^^^^^^^^^^^
以上是 7/10 課程




---






Linux 應用整合實務班
===

課程說明
---

- [課程大綱](/65jn_LU7Rh-8znTQsqmTaQ)
- [線上資源](/w6_XaPsESSuDQ-BP38SDfQ)

2022-07-10
---

- [Kickstart 自動安裝](/rL7-1JJ9SDiLNZS4-7L4xw)
- [設定 Kickstart Server](/60Uo4etkSniCQ0GTnEeOZw)
- [vi 文字編輯器](/DZJs81LGTfKdKem33sIMEA)
- [編輯 myks.ks](/4pZ1jWv2TvmV8w8WmChilQ)
- [使用 myks.ks 安裝](/q5WK3JlTTlyDQ4ia6qxiBg)
- [校時](/NDpWNIEgQlWFIzD5GJIsYg)

2022-07-17
---

2022-07-24
---

[LVM 管理與使用](/VqwWZe1pT7KgwecwJnBjjg)
[LVM 空間擴展](/8sm2QVCFQgSxbtx_Fz-A1g)
[LVM 快照](/vOw2ZtoRS1-UnfOYmgny1A)
[LVM 清除作業](/n7p5CbLvTFyJlXApjZachQ)
[LVM LAB](/UNOvYN2FRAChIv2cNw50sw)



---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 課程資訊

* 課程名稱: Linux 應用整合實務班 第 02 期
* 報名連結: [
台灣就業通 在聯訓練網](https://ojt.wda.gov.tw/ClassSearch/Detail?OCID=143725&plantype=1)
* 訓練單位: 全國勞工聯合總工會
* 講師: 廖子儀
    * 認證: RHCA Level II, LPIC Level 2, Comptia Security+, Comptia CySA+
    * 專長: 企業 Linux 應用導入規劃, 資訊系統整合建置, Open Source 虛擬化規劃與執行, PHP程式設計

## 課程大綱

本課程讓學員瞭解如何使用 Linux 作業系統進行常見的整合機制。

在本課程中，主要內容包含：

| -- | 項目 | 講師 |
| -- | -- | -- |
| 2022-07-10 | 企業營運需求與 Linux 整合概觀 | 廖子儀 |
| 2022-07-10 | 企業版 Linux 選擇與使用 | 廖子儀 |
| 2022-07-17 | Linux 檔案系統與 Windows 檔案分享 | 廖子儀 |
| 2022-07-17 | Linux 檔案分享與 Windows AD 帳號整合 | 廖子儀 |
| 2022-07-24 | Linux 檔案系統卷建立與管理 | 廖子儀 |
| 2022-07-24 | Linux 檔案系統卷快照應用 | 廖子儀 |
| 2022-07-31 | Linux Container容器部署 | 廖子儀 |
| 2022-07-31 | Container 應用與 NFS 儲存管理 | 廖子儀 |
| 2022-08-07 | 反向代理服務應用 – 搭配容器應用 | 廖子儀 |
| 2022-08-07 | 反向代理服務應用 – SSL 憑證與加密 | 廖子儀 |
| 2022-08-14 | MySQL/MariaDB 資料庫 - 調整與設定 | 廖子儀 |
| 2022-08-14 | MySQL/MariaDB 資料庫 – 資料同步作業 | 廖子儀 |
| 2022-08-21 | Linux 應用整合驗收 | 廖子儀 |
| 2022-08-21 | Linux 應用整合案例研究 | 廖子儀 |

## 應用工具

課程應用工具如下：

* [AlmaLinux 8.4](https://rsync.repo.almalinux.org/vault/8.4/isos/x86_64/AlmaLinux-8.4-x86_64-dvd.iso)



---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 線上資源

* [Google Meet](https://meet.google.com/uta-wkjq-vfd) (https://meet.google.com/uta-wkjq-vfd)
* [撥放清單](https://www.youtube.com/playlist?list=PLi8AVVmcS1cLRHmzY4e6vUXSRkLK0syk2)

## 上課環境

* 上課環境會提供遠端主機。請大家操作的電腦確認符合下列規格：

    * **Windows 10/11** 版本，以連線遠端桌面。
    * macOS 請安裝 **Microsoft Remote Desktop** APP (https://apps.apple.com/tw/app/microsoft-remote-desktop/id1295203466?mt=12)

* 遠距上課使用 Google Meet，建議使用 Google Chrome 進行連線。

## Google Meet 測試

1. 點選會議連結後，選擇 [檢查音訊及視訊功能]

    ![](https://i.imgur.com/wsFlVrT.png)

2. 開啟視訊、喇叭等功能

    ![](https://i.imgur.com/r7IOJEL.jpg)

3. 測試各功能是否正常，如果正常則可以順利看到測試錄影結果

    ![](https://i.imgur.com/EghtxuC.jpg)

4. 確認各功能正常後，在上課前點選要求進入會議室

    ![](https://i.imgur.com/xqX0TkF.jpg)




---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# Kickstart 自動安裝

![](https://i.imgur.com/TRnJHxR.png)


安裝完成後重新開機

![](https://i.imgur.com/nOGIWgd.png)



---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 設定 Kickstart Server

## 設定 KS 檔

@Desktop

```
student$ sudo su -

root#
```

```
root# dnf install -y httpd

root# systemctl enable --now httpd

root# firewall-cmd --permanent --add-service=http
root# firewall-cmd --reload
```

```
root# cd /var/www/html/

root# mkdir ks/; cd ks/
root# scp root@172.16.170.1X:~/anaconda-ks.cfg ./myks.ks

root# restorecon -R /var/www/html/
root# chmod +r ./myks.ks
```

Firefox: http://localhost/ks/myks.ks

![](https://i.imgur.com/tYdbjX5.png)

## 設定 BaseOS

@Desktop

```
root# umount /dev/sr0
```

```
root# cd /var/www/html/
root# cd ks/

root# mkdir OS
root# mount /dev/sr0 /var/www/html/ks/OS/

root# ls OS/
```

![](https://i.imgur.com/0PR7Tpi.png)

Firefox: http://172.16.170.X/ks/OS/BaseOS/

![](https://i.imgur.com/NtrE7Iu.png)




---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# vi 文字編輯器

在大部份的 Linux 發行版中，有許多的服務都是要經過設定後才能正確運作，這些設定必須使用編輯器來修改，因此學習一個上手的文字編輯器能夠有效的提升 Linux 管理效率。

在本章節裡介紹的是 `vi` 文字編輯器。`vi` 是歷史悠久且在大部份 Linux 發行版本都包含的內建編輯器，因此瞭解 `vi` 後不旦能夠讓您在 Linux/Unix 中暢行，其它如 \*BSD、macOS 等系統上也能適用。

完整的 `vi` 有很多功能，但大多情況我們會用到的不外乎下列功能：

* 文字編輯
* 游標移動
* 存檔
* 文字搜尋
* 離開

等幾個常用功能，以上幾個項目也涵蓋了大部份的文字編輯作業，所以在本章節中將協助讀者簡單且快速的操作 `vi`。

在 `vi` 編輯器中，會有 3 個主要模式，分別如下：

* 編輯模式
* 一般模式
* 指令模式

每一模式若要離開的話是使用鍵盤上的 [ESC] 鍵。也是 **一般模式**。以下我們就針對常用的部份進行說明。

## 一般模式

在一般模式中，我們可以對文件上的游標進行控制。

| 功能 | 按鍵 | 
| -------- | -------- |
| 游標往上     | [k]     |
| 游標往下     | [j]     |
| 游標往左     | [h]     |
| 游標往右     | [l]     |
| 游標移到第 1 行     | 1G     |
| 游標移到第 5 行     | 5G     |
| 游標移到第 n 行     | `n`G (`n` 為數字)     |
| 游標移到最後行     | G     |
| 游標移到行首     | ^     |
| 游標移到行尾     | $     |

下列方式可以進行文件操作。

| 功能 | 按鍵 | 
| -------- | -------- |
| 複製     | yy     |
| 複製 2 行     | 2yy     |
| 複製 n 行     | `n`yy (`n` 為數字)     |
| 在下一行貼上     | p (小寫英文)     |
| 在上一行貼上     | P (大寫英文)     |
| 剪下一個字元     | x     |
| 剪下 2 個字元     | 2x     |
| 剪下 n 個字元     | `n`x (`n` 為數字)     |
| 刪除一整行     | dd     |
| 刪除二行     | 2dd     |
| 刪除 n 行     | `n`dd (`n` 為數字)     |

## 指令模式

指令模式通常是在一般模式中，直接輸入以 `:` 為開頭就會進入指令操作。

常用的指令如下所示：

| 功能 | 按鍵 | 
| -------- | -------- |
| 存檔     | :w     |
| 離開     | :q     |
| 存檔後離開     | :wq     |
| 不存檔離開     | :q!     |
| 強制存檔     | :w! (需要有相關權限)     |
| 尋找字串     | /`{word}` (`{word}` 代表要找的字串)     |

## 編輯模式

在編輯模式裡，鍵盤上輸入的字符都會反應到檔案的本文中，也就是開始進行文件的編輯。使用下列的方式，可以從 **一般模式** 中進入編輯模式。

常用進入編輯模式的方法如下所示：

| 功能 | 按鍵 | 
| -------- | -------- |
| 在目前位置開始編輯     | i     |
| 在游標所在的下一字元開始編輯     | a     |
| 在目前所在行下方新增新的一行後開始編輯     | o     |
| 在目前所在行上方新增新的一行後開始編輯     | O     |

在編輯模式中，如要回到一般模式，可以按下 [ESC]。

## 留意事項

`vi` 啟動時，會在文件所在位置產生一個暫時性的交換檔案，這個交換檔案會在 `vi` 關閉時自行刪除，如果沒有進行正確的關閉方式，那麼這個交換檔就會被留下來，當您再次開啟該檔案時可能會出現警告的訊息。





---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 編輯 myks.ks

@Desktop

```
root# cd /var/www/html/ks/

root# cp myks.ks myks.ks_backup
```

```
root# vi myks.ks
```

```=
修改
...

L12:
chrony

L26,L27
#url --url="http://172.16.60.253/alma8/repo/BaseOS/"
url --url="http://172.16.170.X/ks/OS/BaseOS/"
```

```
root# diff myks.ks myks.ks_backup
```

![](https://i.imgur.com/Y2l3P0w.png)


---
tags: 全勞聯_Linux-Integration-02, 全國勞工聯合總工會
---

# 使用 myks.ks 安裝

## 清空 Server

@Server

```
root# dd if=/dev/zero of=/dev/vda bs=1M count=10
```

```
root# reboot
```

## 重新安裝 Server

1. 開啟 Open-Console
2. 設定參考的 Kickstart
  






