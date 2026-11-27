# p6 二维码（静态码 / 印刷）

- URL: https://kdb-wind.github.io/copycat-dev/p6/
- 人群：要印贴纸 / 海报 / 名片 / 门店码的小店主与活动运营
- 需求类型：**半常年**——开业、活动、上新时集中，平时零星
- 一句话卖点：静态码、不注册、不加水印、能导 SVG（印刷用）

## 中文帖子（可直接复制）

### 1) 小红书 · 口吻：开店印贴纸踩的坑

> 第一次印二维码踩了三个坑：
> ① 印太小。名片上放 1.5cm，手机怎么都对不上焦，后来改 2.5cm 才行。
> ② 把码塞进色块里，四周留白被裁掉——那是「静区」，裁了就扫不出来。
> ③ 用了个免费网站，注册后才给高清图，还带它自己的水印。
> 静态码其实不用注册：内容直接编进方块里，谁都能生成，扫一辈子不用回它网站。

### 2) B站评论区 · 口吻：给做物料的

> 印刷的二维码别用 JPG，用 SVG 或 PNG 原尺寸，别让排版软件再压一次。
> 另外留白（静区）至少 4 个模块，别为了好看裁掉；深色码浅色底，别反色。
> 要放 logo 就把容错调到 H，且别超过码面积 20%。

### 3) 知乎回答 · 口吻：回答「免费二维码生成器为什么都要注册」

> 因为免费额度通常给的是**动态码**：码里存的不是你的网址，而是对方服务器的短链。注册了它才能统计扫码次数，也才能在你不续费时把码关掉。
> **静态码**把内容直接编进图案里，不需要任何人维护，所以没有理由要你注册——这类工具通常是纯前端，连服务器都没有。
> 怎么判断：生成后断网，还能扫出来就是静态码；扫出来先跳到某个短域名再跳转，多半是动态码。
> 需要统计扫码量就用动态码，认这个成本；只是印个门店链接，静态码够了。我常用的这个能导 SVG：https://kdb-wind.github.io/copycat-dev/p6/

## 英文帖子 ×2

### r/smallbusiness

> Title: Your QR code doesn't need an account — check for the redirect
>
> Most "free QR generator" sites hand you a dynamic code: the QR contains their short URL, not yours. That's how they count scans — and how your printed menu stops working if you stop paying.
>
> A static QR encodes your URL directly. Test: generate it, turn off wifi, scan. If it resolves without a redirect through someone else's domain, it's static and it will work as long as the pattern is readable.
>
> Print notes that matter more than the generator: at least 2cm square, keep the 4-module quiet zone, dark modules on light background, SVG for anything going to a printer.
>
> Browser-only generator I use (static, no account, SVG export): https://kdb-wind.github.io/copycat-dev/p6/

### r/Etsy

> Title: QR codes on packaging — what actually survives printing
>
> Three things break printed QR codes: too small (<2cm), a cropped quiet zone (the blank border is part of the spec), and re-compressing a PNG into JPG in the layout tool.
>
> Ask your printer for the code as SVG. If you must use raster, export at final physical size × 300dpi and don't let anyone "optimize" it.
>
> For generating: a static code (content embedded, no redirect) is enough for a shop link, and it can't be switched off later by a service you forgot about. I use this one, no account needed: https://kdb-wind.github.io/copycat-dev/p6/

## 目标社区（具体）

- 知乎：问题「免费二维码生成器哪个好」「二维码会过期吗」；话题「开店」「实体店」「印刷」
- 小红书：话题标签 `#开店` `#实体店` `#摆摊` `#海报设计` `#印刷`
- B站：搜「开店日常」「物料印刷」类视频，评论区补充
- Reddit：`r/smallbusiness`、`r/Etsy`、`r/BarOwners`、`r/graphic_design`（后两个对 self-promo 严格，只回答问题）
- 豆瓣：`开店笔记`类小组（先潜水，看组规是否允许工具帖）

## 时间窗

- **半常年**：开学季（社团招新物料）、开业季（3–4 月、9–10 月）、双十一前（门店促销物料）是高峰。
- 平时靠回答「二维码会不会过期」「为什么扫不出来」这类常青问题带量。
- 建议首发：知乎那两个问题各答一次，隔天发，不要同一天。

## 硬规则（每份都照做）

1. 同一账号、同一平台，**每天只发一条**。
2. **先回答别人的问题，再谈自己的工具**；扫描失败类问题最好答，答完别急着贴链接。
3. 不许开小号、不许群发、不许在同一个帖子下重复贴链接。
4. 不许说「永久有效」——你的页面在，码就在；页面挂了，静态码指向的网址一样会 404，别给假承诺。
