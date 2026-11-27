# p1 中文标点 / 全半角 / 繁简转换

- URL: https://kdb-wind.github.io/copycat-dev/p1/
- 人群：公众号 / 小红书写作者、论文与公文排版的人、从 PDF 抄字的人
- 需求类型：**常年**，没有季节窗口；开学季和年底总结季略高
- 一句话卖点：不只是「换标点」，还能看见改了哪里，繁简双向

## 中文帖子（可直接复制）

### 1) 小红书 · 口吻：写公众号踩的坑

> 从 PDF 里复制一段话进编辑器，标点全是半角，汉字之间还带空格，一段 500 字我能手动改 20 分钟。
> 后来学乖了：先过一遍自动整理，再自己读一遍。顺序很重要——先机器后人工，人工只改语气，不改标点。
> 我用的那个还能标出「哪里被改了」，黄底是加的、划线是删的，胆子大一点也不会改坏原意。
> 唯一的坑：代码块别丢进去，引号会被动。

### 2) B站评论区 · 口吻：补充工具

> 补充一个我常用的：粘贴进去点一下，中文标点、中英文间距、多余空行一起处理，繁简也能互转。
> 好处是它会标出改了哪几处，不是黑箱；坏处是不认代码块，贴代码别用它。
> 搜「中文标点转换 在线」应该能找到，不用注册。

### 3) 知乎回答 · 口吻：回答「有什么整理中文标点的工具」

> 分两种情况说。
> 如果你只是偶尔改一段：手工改比找工具快，别折腾。
> 如果你是每天要处理几千字（公众号、论文、公文）：值得用一个能批量、能看见 diff 的工具。判断标准有三条——① 会不会把英文里的逗号也换成全角（好的不会，它看上下文）② 能不能关掉单条规则（有人就是要把 `·` 留着）③ 改了哪里能不能看见。第三条最容易被忽略，但它是你敢不敢用的关键。
> 我自己常用的是一个网页版，粘贴即用、本地处理不上传，繁简也能互转。链接放这儿，自己判断合不合手：https://kdb-wind.github.io/copycat-dev/p1/

## 英文帖子 ×2

### r/ChineseLanguage

> Title: If you paste Chinese text from a PDF and the punctuation comes out half-width
>
> Two things are usually happening: the punctuation is ASCII `, . ? !` instead of `，。？！`, and there are stray spaces between characters (a PDF extraction artifact). Manually fixing 500 characters takes ~20 minutes, and you will miss some.
>
> What works: run a punctuation/spacing pass first, then read it once for tone. Doing it in the other order wastes the read. Watch out for code blocks — a general-purpose cleanup will rewrite quotes inside code.
>
> I built a small page for this (runs locally, no signup): https://kdb-wind.github.io/copycat-dev/p1/ — it also highlights what changed, which is the part I actually trust.

### r/translator

> Title: Cleaning up punctuation when you paste Chinese source text
>
> If you are translating from a Chinese PDF, the source often arrives with half-width punctuation and inter-character spaces. Translating that as-is makes the target text read oddly, because sentence boundaries are ambiguous without `。`.
>
> My workflow: normalize punctuation and spacing on the source first, keep the original in a second tab, then translate. The normalization step takes seconds and saves re-reading later.
>
> Tool I use (browser-local, no upload): https://kdb-wind.github.io/copycat-dev/p1/

## 目标社区（具体）

- 知乎：话题「中文排版」「公众号运营」「Markdown」，以及问题「如何批量替换中文标点」「全角和半角有什么区别」
- 小红书：话题标签 `#公众号排版` `#中文写作` `#论文格式` `#排版强迫症`
- B站：搜「公众号排版教程」「Word 排版」类视频，只在**评论区**补充，不发视频
- Reddit：`r/ChineseLanguage`、`r/Chinese`、`r/translator`（先看各版 self-promotion 规则，r/ChineseLanguage 允许在回答里带工具链接）
- V2EX：`/go/create` 或 `/go/qna`，按「分享创造」格式发，标题写清解决了什么

## 时间窗

- 没有窗口，随时可发；**开学季（8 月底–9 月中）和年底总结季**回帖转化最好。
- 建议首发：挑一个知乎现有问题回答（不是新开问题），当天只发这一条。

## 硬规则（每份都照做）

1. 同一账号、同一平台，**每天只发一条**。
2. **先回答别人的问题，再谈自己的工具**；只贴链接不回答＝广告，会被删。
3. 不许开小号、不许群发、不许在同一帖子下重复贴链接。
4. 链接只放在第 3 条（知乎）和英文帖的最后一句，前两条只讲做法。
