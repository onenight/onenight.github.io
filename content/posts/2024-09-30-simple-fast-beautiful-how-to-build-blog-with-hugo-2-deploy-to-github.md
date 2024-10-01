---
title: "簡單、快速、美觀：如何用 Hugo 打造專屬部落格 (二)：部署到 Github Pages"
date: 2024-09-30T21:46:07+08:00
draft: false
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

請先到 [Github](https://github.com/)，並新增一個 _repository_。 repo 命名請使用 `YOUR_USERNAME.github.io`，例如我的 _username_ 是 onenight，那我就輸入 `onenight.github.io`

![新增 Github Pages repo](/images/init_github_page_repo.jpg)

## 2. 連結本地端與遠端的 repo

新增成功後，你看到的成功畫面應該長這樣。 然後先不要關掉視窗，請將紅色框框內的指令記起來，我們等等會用到。

![成功建立 repo](/images/init_github_page_repo_success.jpg)

回到我們的 `terminal`，並依序把上面的指令輸入。

先建立本地端的 repo 和遠端的 repo 連結，我們要更新到遠端才知道是哪個 repo。

```
git remote add origin git@github.com:onenight/onenight.github.io.git
```

然後把 _branch_ 命名改掉 (_官方預設名稱叫 main_)

```
git branch -M main
```

接著更新記錄到遠端的 repo

```
git push -u origin main
```

## 3. 啟用遠端 workflow

_workflow_ 是 Github 的一個自動化服務，它可以偵測 repo 的更新，並依據腳本自動處理。 這次我們要使用的是 hugo 腳本。

回到 Github，在 repo 右上角找到 **Settings > Pages** 頁面，並依照圖片說明設定 _source_ 為 _Github Actions_。 完成後，我們點擊並進入 _browse all workflows_ 頁面

![設定 Github Action](/images/set_up_action.jpg)

搜尋 _hugo_ 並點擊 _configure_ 按鈕

![搜尋 Hugo Action](/images/search_hugo_action.jpg)

點擊右上角的 _Commit changes_，並再次點擊彈出視窗的 _Commit changes_ 就完成設定， _workflow_ 也會自動啟用

![儲存 Hugo configure](/images/save_hugo_configure.jpg)

接著回到上方 **Actions** 頁籤來查看 _hugo workflow_ 狀態，綠燈就表示大功告成 🙌

![檢查 workflow 狀態](/images/check_workflow_status.jpg)

最後我們再回到 `terminal` 輸入以下指令，把 _workflow_ 設定檔下載到本地端。 後續我們上傳更新，它就會自動執行。

```
git pull
```

# 開始部署

恭喜你看到這裡，假如你前面都有跟著步驟做，那你已經默默地完成第一次的部署了！

在瀏覽器輸入 `https://YOUR_USERNAME.github.io`，你應該可以看到自己的部落格正在運行中 🎉🎉🎉

那你是怎麼部署的呢？

![部署流程](/images/deploy_flow.jpg)

在初始化設定完成後，想要發表新的內容，基本上我們只剩下兩個步驟要做 1. 儲存 2. 上傳。

現在我們就來試看看發布文章吧！

請先到文章的 `.md` 檔案，把開頭的草稿設定改成 `false`

```
draft: true
```

接著儲存更新的檔案 (這一步我們前一篇有學到)

```
git add.
git commit -m "Your Messages"
```

最後上傳

```
git push
```

# 小結:

本篇我們介紹了如何部署到免費的 *Github Pages*服務，並一步步地做好初始化設定，最終完成部署。 而下一篇，我們會再介紹部落格的其他設定以及功能！

> ### 系列文章
>
> [簡單、快速、美觀：如何用 Hugo 打造專屬部落格 (一)：撰寫你的第一篇文章](/2024-09-28-simple-fast-beautiful-how-to-build-blog-with-hugo-1)
