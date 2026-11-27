# p2 线索抽取（邮箱 / 电话 / 链接 / 金额）

- URL: https://kdb-wind.github.io/copycat-dev/p2/
- 人群：招聘 / 销售 / BD / 做调研的人
- 需求类型：**常年**，招聘季（3–4 月、9–10 月）和展会季略高
- 一句话卖点：一段乱文本进，去重后的一张表出，可导 CSV

## 中文帖子（可直接复制）

### 1) 小红书 · 口吻：招聘狗的日常

> 面了 30 个人，简历里的手机号散在正文各处，我要一个个复制进表格，40 分钟没了，还漏了两个。
> 后来改成：把简历正文全选粘进一个框，一次抽出所有手机号和邮箱，自动去重，再倒回表格。
> 注意看一遍——有人把公司总机也写在简历里，那个不该当候选人电话。

### 2) B站评论区 · 口吻：做调研的

> 一条经验：从网页复制出来的一堆文字，直接丢进表格会乱行，先把邮箱/链接单独抽出来，再去重，最后才排版。
> 去重这步别省，同一批内容复制两次很常见。
> 抽完人工核一遍手机号，抄错的号码工具救不了。

### 3) 知乎回答 · 口吻：回答「怎么批量提取文本里的邮箱和电话」

> 三种办法，按场景选：
> ① 数据在 Excel 里：用正则公式或 Power Query，最稳，但要会写。
> ② 数据在几十个网页里：先复制成文本，再用正则工具批量抽；记得先去重再排序。
> ③ 一次性、量不大：直接网页工具，把一段话粘进去，勾上要抽的类型。
> 判断工具好坏看两点——**会不会把订单号当手机号**（好的会按 11 位 + 1 开头挑），以及**去重规则**（同一个号写成 +86 138-1234-5678 和 13812345678 应该合成一个）。
> 我常用的那个还能加自己的正则，规则可以生成链接发给同事：https://kdb-wind.github.io/copycat-dev/p2/

## 英文帖子 ×2

### r/sales

> Title: Pulling emails and phones out of a wall of text without a CRM
>
> When you paste 40 inbound emails into one doc, the manual step is not "find the email" — it's deduping it afterwards. Same person shows up as `+1 415-555-0134` and `4155550134`, and now you have two records.
>
> What I do: extract, normalize (strip spaces/dashes and country code before comparing), dedupe, then paste into the sheet. Takes a minute instead of fifteen, and nothing gets dropped.
>
> Small browser tool that does this, plus a custom regex field if your IDs have a pattern: https://kdb-wind.github.io/copycat-dev/p2/

### r/recruiting

> Title: Deduping candidate contacts before they hit the ATS
>
> The failure mode is silent: you paste a batch of candidate details, the ATS creates two records for the same phone number because one came with `+86` and one didn't. Cleaning that up later costs more than the original import.
>
> Normalize before import — strip separators and country prefixes, dedupe on the normalized value, keep the original formatting in a second column if you still need to dial it.
>
> I use this for the cleanup step (local only, no upload): https://kdb-wind.github.io/copycat-dev/p2/

## 目标社区（具体）

- 知乎：问题「怎么批量提取邮箱」「Excel 怎么提取手机号」；话题「招聘」「销售」「数据整理」
- 小红书：话题标签 `#招聘日常` `#HR` `#销售` `#效率工具`
- B站：搜「Excel 提取」「正则表达式入门」，评论区补充
- Reddit：`r/sales`、`r/recruiting`、`r/excel`（r/excel 只接受回答问题，别发工具帖）
- 脉脉：职场话题下回答，不发帖——脉脉对推广极敏感

## 时间窗

- **常年**，招聘季（3–4 月、9–10 月）和广交会/展会前后略高。
- 建议首发：知乎「怎么批量提取邮箱」，工作日晚上 8–10 点答。

## 硬规则（每份都照做）

1. 同一账号、同一平台，**每天只发一条**。
2. **先回答别人的问题，再谈自己的工具**；r/excel 这类版块只回答，不提工具也完全可以。
3. 不许开小号、不许群发、不许在同一个帖子下重复贴链接。
4. **不要教人爬别人网站**——这条写进帖子里，别让工具被当成采集器。
