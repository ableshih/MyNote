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
