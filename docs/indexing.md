# 收录：已经做了什么、还要谁来做

目标不是「页面能打开」，是「有人在搜索里能找到」。这两件事之间隔着一次外部流程，下面把已经做完的和必须由主理人做的分开写。

## 已经做完（我这边能做的都做了）

| 项 | 状态 | 证据 |
|---|---|---|
| `robots.txt` | 线上 200，允许全部，指向 sitemap | https://kdb-wind.github.io/copycat-dev/robots.txt |
| `sitemap.xml` | 线上 200，XML 结构校验通过，7 条 URL | https://kdb-wind.github.io/copycat-dev/sitemap.xml |
| 每页 `canonical` | 7 页各一条，指向自己的正式 URL | 源码 `<link rel="canonical">` |
| 每页 `<title>` | 长尾搜索句式（不是产品名） | 见 REPORT-R3 的 A 节 |
| 每页正文 | p2 +369 字 / p3 +341 字问答段 | 页面可读 |
| **IndexNow 提交** | 7 个 URL 已提交，接口返回 **202 Accepted** | 见下方「IndexNow」 |
| IndexNow key 文件 | 线上 200 | `https://kdb-wind.github.io/copycat-dev/4c7bc0584472b703fbfdf2e4f5bccf37.txt` |

## IndexNow 是什么、为什么用它

Bing / Yandex / Naver / Seznam 之间共享的一套「主动告知」协议：你在自己站点根目录放一个 key 文件证明所有权，然后 POST 一批 URL，它们就会来抓。**不需要注册账号**，这是它和 Google Search Console 最大的区别。

- 提交接口：`POST https://api.indexnow.org/indexnow`
- 本次返回：`202 Accepted`（表示已接收，进入抓取队列；不等于被收录）
- 提交内容记录在仓库 `.check/indexnow.json`（已 gitignore，需要复现可照下面重发）：

```json
{
  "host": "kdb-wind.github.io",
  "key": "<仓库根那个 32 位文件名，不带 .txt>",
  "keyLocation": "https://kdb-wind.github.io/copycat-dev/<key>.txt",
  "urlList": ["https://kdb-wind.github.io/copycat-dev/", "... p1/ … p6/"]
}
```

> 注意：`host` 是 `kdb-wind.github.io`（Pages 的域名），不是仓库名。改了 key 或换了域名必须同步改这三处。

## 必须由主理人做的（要账号，我不代做）

1. **Bing Webmaster Tools**（免费，5 分钟）
   - 用同一个 GitHub 账号登录 → 添加站点 `https://kdb-wind.github.io/copycat-dev/`
   - 验证方式选「导入 GitHub Pages」最简单
   - 然后 `Sitemap` → 提交 `sitemap.xml`
   - 验收：**1–3 天后**看 `URL 检查` 里状态是不是「已编入索引」
2. **Google Search Console**（免费，5 分钟）
   - 添加「网址前缀」属性 `https://kdb-wind.github.io/copycat-dev/`
   - 验证用 HTML 标签：把那段 `<meta name="google-site-verification">` 加进根 `index.html` 的 `<head>`，push，再点验证
   - `站点地图` → 提交 `sitemap.xml`
   - 验收：**3–14 天**后 `网页` 报告里出现「已编入索引」的页面数
3. **统计**（GoatCounter / Plausible / Cloudflare 三选一，见 `dist/tracking.md`）

## 验收口径（外部数据，不接受自评）

按主理人定的口径，这一环的完成标准只有三个，任何一个都不能用「我觉得」代替：

1. **收录**：Search Console / Bing 后台里，7 个 URL 中有 ≥1 个状态为「已编入索引」。
2. **入口**：`tracking.md` 里至少有 1 行填了「有回复」，且回复内容进入第 2 档（在讨论方法，不只是骂广告）。
3. **真实收益**：第一笔真实收入 —— 今晚没接支付，所以这一项必然是 0，不要伪造。

## 一个现实预期

新站 + 没有外链 + 内容只有几段问答，Google 通常**两到四周**才开始给零散长尾词流量，Bing 快一些（几天）。所以接下来两周的正确动作是：

- 每周往 `dist/` 的渠道表里填两条真实发布记录；
- 不要因为三天没流量就改标题——改标题会让已经开始的抓取重新排队；
- 真要加速，唯一可控的是**外链**：把页面回答发到知乎/Reddit，本身就是外部链接，这是穷人的 SEO。
