---
title: Hexo+Github
date: 2018-05-04 21:33:07
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

```
npm install hexo-cli -g    #安裝Hexo框架
hexo init blog             #初始化blog資料夾
cd blog                    #切換至blog資料夾
npm install                #安裝npm套件
hexo server                #啟動local端server
```

在D槽先建立一個資料夾名稱，進入此資料夾右鍵使用Open with Code，開啟整合式終端機快捷鍵**Ctrl+\`**依序輸入上面1~5的步驟
接著打開瀏覽器輸入localhost:4000，進入部落格的世界~

![hexo](/img/hexo.png)

## 更換部落格主題
到[HEXO的官網](https://hexo.io/themes/)尋找主題，這邊以主題：NexT當範例

![NexT](/img/NexT.png)

開啟整合式終端機輸入紅框處主題載點

`git clone https://github.com/theme-next/hexo-theme-next themes/next`

找到部落格框架的設定檔(\_config.yml)theme：後進行修改

![theme](/img/theme.png)

接著再找到language： zh_TW和timezone： Asia/Taipei進行修改讓部落格設定成支援繁體中文與台灣時區

![lan](/img/lan.png)

再到剛剛下載的主題資料夾進行更名(**next**)並將.git資料夾刪除(**隱藏檔**)

![git0](/img/git0.png)

## 新建一篇部落格文章

`hexo new "文章名稱"`

![blog](/img/blog.png)

## 部落格推送到Github

將部落格推送到Github前，先來瞭解一下推送的流程。

![hexogd](/img/hexogd.png)

![repo](/img/repo.png)

找到部落格框架的設定檔(\_config.yml)deploy：後進行修改並存檔

`deploy:`
`type: git`
`repo: git@github.com:你的ID/你的ID.github.io.git`
`branch:master`

![git](/img/git.png)

然後安裝Git佈署套件(開啟整合式終端機輸入指令)

`npm install hexo-deployer-git --save`

在輸入

`hexo g #編譯成靜態檔案`
`hexo d #佈署到倉庫`

開啟瀏覽器輸入 你的ID.github.io 就能看到部落格成功丟上去了

## 其他台電腦進行發佈文章

登入Github 建立一個新倉庫 命名為blog

![cblog](/img/cblog.png)

到D槽進入剛剛自行建立的資料夾裡找到blog資料夾，右建使用Open with Code開啟後並於整合式終端機輸入

`git init #初始化這個目錄，讓 Git 對這個目錄進行版控`

安裝[tortoisegit](https://tortoisegit.org/)後

![tortoisegit](/img/tortoisegit.png)

設定部落格文章原始檔 傳送至 剛剛新建的倉庫(blog)

![tortoise](/img/tortoise.png)

開啟Tortoisegit setting -> GIT -> Remote 並設定

`Remote: origin`
`URL: git@github.com:你的ID/blog.git`

設定Tortoisegit使用git的ssh程式推送

![ssh](/img/ssh.png)

Commit後在點選推送就會傳送到倉庫(blog)

![commit](/img/commit.png)

