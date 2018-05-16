---
title: 產生ssh key for github
date: 2018-04-08 22:07:07
tags:
---
在建立ssh key時請先安裝[git for windows](https://git-scm.com/download/win)套件。
設定Github上的名稱與註冊電子信箱
        git config --global user.name "github名稱"
        git config --global user.email "github註冊的電子信箱"

使用github的倉庫時可以透過兩種方式來進行提取/存放分別是Https或ssh，若選用Https來進行操作的話，每次推送到倉庫時都必須輸入github帳號密碼，如果使用ssh方式，只要到github上設定public key，後續進行任何操作就不需要再次輸入github帳號密碼。
<!-- more -->
開啟 命令提示字元輸入以下來檢查是否有相關檔案

        ls -al ~/.ssh

如果沒有ssh key，透過以下步驟製作ssh key
1、開啟 命令提示字元

2、輸入下列指令， 並在 ""中輸入自己的github mail

        ssh-keygen -t rsa -b 4096 -C "GitHub email address"

3、出現設定ssh key密碼(這邊直接enter略過)

4、完成後會出現如下畫面

![ssh0](/img/ssh0.png)

5、輸入以下指令，複製ssh key貼到記事本

        clip < ~/.ssh/id_rsa.pub

6、登入到github頁面中，點選右上頭像後點選 Settings後，在點選左手邊的SSH and GPG keys

![ssh2](/img/ssh2.png)

7、選擇 New SSH key

![ssh3](/img/ssh3.png)

8、貼上剛剛複製到記事本上的ssh key並給這個key一個名稱

![ssh4](/img/ssh4.png)

9、增加ssh key後測試是否有連結成功，開啟**命令提示字元**

10、輸入以下指令

        ssh -T git@github.com

11、輸入yes後如出現以下訊息就表示連結成功

![ssh1](/img/ssh1.png)