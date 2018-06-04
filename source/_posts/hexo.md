---
title: Hexo+Github
date: 2018-06-04 21:33:07
tags:
---
## 什麼是 Hexo？
Hexo是一個快速、簡單且強大的部落格框架。我們可以透過Hexo將Markdown語法轉換成HTML靜態網頁。

## Hexo特色：

* 用Markdown語法寫blog
* 多種網站主題與插件可供選擇
* 輕易部署到Github Pages
<!-- more -->

## 安裝Hexo

Hexo由Node.js寫成，所以在使用Hexo前需先安裝[Node.js](https://nodejs.org/en/)套件。
![nodejs](/img/nodejs.png)
裝完後再接下來的過程中會使用到[Visual Studio Code](https://code.visualstudio.com/Download)與[TortoiseGIT](https://tortoisegit.org/)，需先安裝這2套軟體。
備註：安裝Visual Studio Code過程需將紅框處打勾
![vsc](/img/vsc.png)

`npm install hexo-cli -g    #安裝Hexo框架`
`hexo init blog             #初始化blog資料夾`
`cd blog                    #切換至blog資料夾`
`npm install                #安裝npm套件`
`hexo server                #啟動local端server`

在D槽先建立一個資料夾名稱，進入此資料夾右鍵使用Open with Code，開啟整合式終端機(快捷鍵<kbd>Ctrl + <kbd>\`</kbd></kbd>)依序輸入上面1~5的步驟
接著打開瀏覽器輸入localhost:4000，進入部落格的世界~

![hexo](/img/hexo.png)

新建一篇部落格文章

`hexo new "文章名稱"`

![blog](/img/blog.png)

將部落格推送到Github前，先修改部落格框架的設定檔(\_config.yml)後進行存檔

`deploy:`
`type: git`
`repo: git@github.com:你的ID/你的ID.github.io.git`
`branch:master`

![git](/img/git.png)

然後安裝Git佈署套件(整合式終端機輸入指令)

`npm install hexo-deployer-git — save`

在輸入

`hexo g #編譯成靜態檔案`
`hexo d #佈署到倉庫`

開啟瀏覽器輸入 你的ID.github.io 就能看到部落格成功丟上去了