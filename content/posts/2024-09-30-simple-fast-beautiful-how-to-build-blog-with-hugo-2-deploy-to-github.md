---
title: "簡單、快速、美觀：如何用 Hugo 打造專屬部落格 (二)：部署到 Github Pages"
date: 2024-09-30T21:46:07+08:00
draft: true
cover:
  image: "images/github_pages.png"
  alt: "Github Pages"
  caption: "Github Pages"
---

既上一篇我們介紹如何在本地端安裝 Hugo、選擇主題並快速建立文章後，這次來談談如何「部署到 Github Pages」給所有人看到 🤩

本篇大綱如下：

- Github Pages 是什麼？
- 初始化設定
- 開始部署

# Github Pages 是什麼？

[Github Pages](https://pages.github.com/) 是 Github 提供的免費服務，它非常適合用於個人網站、部落格、文件或作品集。只要你將打包好的資料上傳，它便會自動幫你轉換為靜態網站，在網路上供所有人瀏覽。

# 初始化設定

先讓我們進行一些初始化設定，以便後續可以進行部署。 這些設定通常是一次性的，做完你後續不用再理會它 🍰

## 1. 建立遠端 repo

請先到 [Github](https://github.com/)，並新增一個 **repository**。 repo 命名請使用 `YOUR_USERNAME.github.io`，例如我的 username 是 onenight，那我就輸入 `onenight.github.io`

![新增 Github Pages repo](/images/init_github_page_repo.jpg)

## 2. 連結本地端與遠端的 repo

新增成功後，你看到的成功畫面應該長這樣。 然後先不要關掉視窗，請將紅色框框內的指令記起來，我們等等會用到。

![成功建立 repo](/images/init_github_page_repo_success.jpg)

回到我們的 `terminal`，並依序把上面的指令輸入。

先建立本地端的 repo 和遠端的 repo 連結，我們要更新到遠端才知道是哪個 repo。

```
git remote add origin git@github.com:onenight/onenight.github.io.git
```

然後把 **branch** 命名改掉 (現在都叫 main)

```
git branch -M main
```

接著更新記錄到遠端的 repo

```
git push -u origin main
```

## 3. 啟用遠端 workflow

**workflow** 是 Github 的一個自動化服務，它可以偵測 repo 的更新，並依據腳本自動處理。 這次我們要使用的是 **hugo 腳本**

# TBD

首先，我們心中對於 **部署** 這件事情有個概念，它其實就是 **發布到網路上** 這麼簡單。 把你的內容丟到某個可以運行的空間，讓好友、家人、甚至是搜尋引擎機器人都能夠找到。

![部署流程](/images/deploy_flow.jpg)

而這是我們每次要發表新內容的部署流程，只有簡單三步驟。橘色方塊是你需要手動操作，灰色方塊是程式自動化幫你做，在本篇你將輕鬆學會它們。
