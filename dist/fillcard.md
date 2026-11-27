# p3 资料卡（常用填表信息）

- URL: https://kdb-wind.github.io/copycat-dev/p3/
- 人群：一个月要报几次名 / 寄多次快递 / 填多张报销单的人
- 需求类型：**常年但低频**，月底月初（报销、报关）略高
- 一句话卖点：存一次在本机，点一下就复制；不注册、不上传、不跨设备

## 中文帖子（可直接复制）

### 1) 小红书 · 口吻：被填表烦到

> 我这个月填了 4 次报名表、寄了 3 个快递、报了 2 次销，每次都在重打同一串地址和税号。
> 后来把这几行固定信息存成一张卡，填表时点一下复制，整卡也能一次复制成「名称：内容」或表格格式。
> 只存在本机，不上传，也不跨设备——这点对我来说是优点：公司电脑上不想留一份云端副本。

### 2) B站评论区 · 口吻：实用补充

> 一劳永逸的做法不是记在备忘录，是做成「一次复制一个字段」的卡片。
> 备忘录的问题是：你要长按选中、拖到刚好，稍微手抖就多选了。卡片是点一下就好。
> 另外注意：存身份证号这种，别在共用电脑上存，localStorage 没加密。

### 3) 知乎回答 · 口吻：回答「有没有管理常用收货信息 / 填表信息的工具」

> 分三类，看你要什么：
> ① **浏览器自动填充**：一次填全表，最省事；但只认标准字段，内网和政务网站经常失灵，而且要交给浏览器账号同步。
> ② **密码管理器**：地址、身份信息都能存，跨设备；但要付费用一个专门软件，杀鸡用牛刀。
> ③ **一张纯本地的卡片**：只存你手动填的几行，点一下复制单个字段，或者整卡复制成表格。缺点是换设备要自己导出 JSON。
> 我的判断：一个月填三次以上、又不想把信息放云端，选③。我自己做的这个就是这个思路，纯前端：https://kdb-wind.github.io/copycat-dev/p3/

## 英文帖子 ×2

### r/productivity

> Title: Repeated form-filling is a copy-paste problem, not a memory problem
>
> If you fill the same five fields (name, address, tax ID, invoice title) more than twice a month, the bottleneck isn't remembering them — it's the selection step. Memo apps make you long-press and drag; a card that copies a single field per click is faster and less error-prone.
>
> Browser autofill handles whole forms, but only for standard fields — internal portals and government forms usually don't cooperate.
>
> I keep this in a local-only card (localStorage, no account, export to JSON when I change machines): https://kdb-wind.github.io/copycat-dev/p3/

### r/ADHD

> Title: The "fill the same form again" tax, and a one-click fix
>
> The annoying part isn't typing — it's the friction: open memo, find the note, long-press, drag the handles, copy, hope you got the whole thing. Ten seconds of fiddling per field is enough to make you postpone the form for a week.
>
> What helped me: one click = one field copied. No selection, no scrolling. And the whole card can be copied as a table when a form wants everything at once.
>
> Built it as a local page, no account: https://kdb-wind.github.io/copycat-dev/p3/

## 目标社区（具体）

- 知乎：问题「有什么好用的地址管理工具」「报销流程太麻烦怎么办」；话题「效率」「职场」
- 小红书：话题标签 `#效率工具` `#职场` `#报销` `#快递`
- B站：搜「效率工具」「Mac 效率」类视频，评论区补充
- Reddit：`r/productivity`、`r/ADHD`、`r/smallbusiness`（r/ADHD 有严格的 self-promo 规则，**只在评论区回答，别开帖**）
- 豆瓣：`抠门` / `极简生活` 类小组（先看组规，多数禁止推广）

## 时间窗

- **常年低频**，月底（报销）、开学季（报名）、双十一（收货地址）略高。
- 这个产品**不建议主动发帖**：需求太散，主动推会被当广告。策略是守株待兔——只在别人问「怎么管理常用地址」时回答一次。

## 硬规则（每份都照做）

1. 同一账号、同一平台，**每天只发一条**。
2. **先回答别人的问题，再谈自己的工具**；p3 尤其如此，主动发帖＝广告。
3. 不许开小号、不许群发、不许在同一个帖子下重复贴链接。
4. 不许暗示「加密保存」——localStorage 没加密，共用电脑上谁打开都能看，帖子里必须写清楚。
