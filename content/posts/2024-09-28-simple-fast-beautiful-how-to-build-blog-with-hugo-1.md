---
title: "簡單、快速、美觀：如何用 Hugo 打造專屬部落格 (一)：撰寫你的第一篇文章"
date: 2024-09-28T00:27:05+08:00
draft: false
cover:
  image: "images/hugo_blog_image.png"
  alt: "Hugo Blog"
  caption: "The world’s fastest framework for building websites" #
---

# 為什麼選 Hugo？

市面上各種部落格琳瑯滿目，例如 Wordpress、Medium、Blogger、方格子、痞客邦等等。 我選擇 [Hugo](https://gohugo.io/) 作為架站工具的原因有幾點：

- 完全免費
- 編輯簡單快速
- 100% 不受站方管制
- 佈景主題不錯看

# Hugo 是什麼？

Hugo 是用 Go 做的一個靜態網站生成器，它方便編輯且介面簡潔，發布也非常迅速。 你可以在筆電 (本地端) 任意創作並隨時預覽成果。

[Markdown](https://hackmd.io/@eMP9zQQ0Qt6I8Uqp2Vqy6w/SyiOheL5N/%2FBVqowKshRH246Q7UDyodFA?type=book)是它主要撰寫文章的格式。 如果你沒接觸過，可以點連結看介紹，它不難背，但我也沒背過就是，通常是用到才查。

你想加強個人品牌或風格，Hugo 社群亦有豐富的[佈景主題](https://themes.gohugo.io/)。看不慣你也可以自己改，寫一些程式碼即可。

# 快速安裝 Hugo 到 Mac

安裝步驟真的非常簡單，只需下幾個指令就可完成。 安裝過程會用到 [brew](https://brew.sh/) 和 [git](https://github.com/)，沒用過它們的話，建議先去安裝和申請帳號。

## 1. 下載 Hugo

開啟你的 `terminal` 終端機，並輸入以下指令

```
brew install hugo
```

## 2. 建立新 Blog

完成後，我們可以用下方指令建立一個新的 blog。

```
hugo new site blog --format yaml
```

你會得到一個 `blog` 資料夾。 接著請進入

```
cd blog
```

然後請先 `init repo`，我們需要它來記錄和部署

```
git init
```

接著新增 `.gitignore` 的檔案到資料夾裡，並填入我們想忽略的檔案

```
# Hugo build lock file
.hugo_build.lock

# Hugo generated files and directories
/public/
```

## 3. 下載佈景主題

![Hugo Themes](/images/hugo_themes.png)

從[佈景主題](https://themes.gohugo.io/)裡面挑選你中意的主題，進一步瀏覽都可以看到下載指令。 我建議直接選有`submodule`的指令。下載成功後，你會發現 themes 資料夾跑出你的主題。

**PaperMod** 下載指令

```
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

接著找到 `hugo.yaml` 檔案，設定主題

```
baseURL: https://example.org/
languageCode: en-us
title: Your Blog Name
theme: PaperMod
```

# 產生第一篇文章

產生文章的指令很簡單，請參考以下格式：

```
hugo new posts/你的文章標題.md

```

它會在 `content` 的資料夾產生 `posts/你的文章標題.md` 文章。 草稿大概長這樣

```
---
title: '簡單、快速、美觀：如何用 Hugo 打造專屬部落格 (一)：撰寫你的第一篇文章'
date: 2024-09-28T00:27:05+08:00
draft: true
---
```

接著請再輸入以下指令，讓我們把 hugo 跑起來。

```
hugo server -D
```

成功跑起來的話，你會看到在訊息中看到 `http://localhost:1313/` 的預覽網址。 請在瀏覽器輸入網址，便可以獲得一個即時預覽的部落格 (本地端)。 你修改存檔的內容，它立即重新編譯並顯示。

![預覽部落格](/images/preview_blog.png)

最後如果你的文章都編寫完畢，請輸入 `git commit` 存檔 💾，以免修改記錄不見

```
git commit -m "Your Messages"
```

# 小結

在本篇文章中，我們介紹了如何用 Hugo 安裝並啟動一個基本的部落格網站，也介紹如何設定佈景主題，以及建立文章。

在接下來的文章中，我們將進一步了解如何發布你的第一篇部落格文章，讓我們繼續探索吧！
