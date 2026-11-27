模型: opencode-go/deepseek-v4.1-flash

P1 tidytext（文本整理器） | 状态: 已上线 | URL: https://kdb-wind.github.io/copycat-dev/p1/
  一句话: 给从 Word / 微信 / PDF 复制文字出来发布的人，把乱标点、中英文间距、空行一次理顺。
  数据: `ios_6764243413` 文本工具箱（月入 $93，213 天，「3 步内完成文本处理」）；同向 `ios_6815114927`
  自检: 5/5。①输入区 textarea#input ②示例跑出「改了 20 处」，输出 `昨天我去了一趟超市，买了两瓶水。顺便看了一下 iPhone 15 的价格，居然要 5999 元？！` ③点「复制结果」提示「已复制」 ④375px scrollWidth=375（docs/shots/p1-375.png）⑤console/errors 均空
  下一步: 加码——再加「繁简」「引号成对」「导出 Markdown」三条，这个是最容易被人搜到的

P2 extract（线索抽取器） | 状态: 已上线 | URL: https://kdb-wind.github.io/copycat-dev/p2/
  一句话: 给从聊天记录、报价单里抄联系人的销售 / 招聘 / BD，把邮箱、电话、链接、金额抽成去重表。
  数据: `ios_6815114927` 试试看工具（46 天，月入 $255，主打识别网址/邮箱/电话/数字）；同向 `ios_6751640981`
  自检: 5/5。①textarea#input + 四个类型开关 + 自定义正则输入框 ②示例抽出「9 条」（邮箱 2 / 电话 1 / 链接 2 / 金额 4），+86 138-1234-5678 与 13812345678 已去重 ③「复制全部」提示「已复制」、CSV 走 Blob 下载 ④scrollWidth=375（docs/shots/p2-375.png）⑤console/errors 空；正则写错时页面给「正则写错了：Unterminated group」而不是白屏
  下一步: 加码——把「去重 + 自定义正则」做成可分享的规则链接（#rule=），这是唯一有传播性的点

P3 fillcard（资料卡） | 状态: 已上线 | URL: https://kdb-wind.github.io/copycat-dev/p3/
  一句话: 给反复填报名表 / 寄件单 / 报销单的人，姓名、地址、税号存一次，点一下复制。
  数据: `ios_6775105307` 表格速填（月入 $205，177 天，「快速查找、一键复制」）；同向 `ios_6772848670`
  自检: 5/5。①七个字段输入框 + 「加一项」 ②填入姓名/手机/邮箱后角标变「3 项已填」，刷新后仍在（localStorage 生效） ③点「复制」提示「已复制：张三」；另有整卡两种格式、导出/导入 JSON ④scrollWidth=375（docs/shots/p3-375.png）⑤console/errors 空
  下一步: 丢或小改——价值真实但最容易被系统自带「自动填充」吃掉；除非加「一键填表脚本」否则不加码

## 卡在哪

1. **MCP 调用**：`search_apps` 第一次按 GOAL 之外的参数名 `q` 调用，被工具拒绝（`Invalid arguments ... query: Missing key`），用 `query` 重试了一次才拿到数据。两次额度用在这两次上，之后没再查。
2. **本机没有可用的 headless Chrome**：`msedge --headless=new --dump-dom` 退出码 0 但 stdout 为空（stderr 也是空），拿不到 DOM。改用已装的 `agent-browser` 做 375px 实测与 console 抓取，所以自检里的「console 无报错」是 agent-browser `errors`/`console` 的输出为空，不是 Chrome DevTools 截图。
3. **页面里有两处真实 bug 是上线后才发现的**，都已修好并重新验证：①`font:600 15px/1 inherit` 这个简写非法（CSS 规范里 `inherit` 不能出现在 font 简写中间），整条声明被丢弃，按钮退回 13.3px Arial；②`.copied` 高亮态只换了底色没换字色，复制按钮会白字白底 600ms。
4. **支付没接**：`BUY_URL` 三个页面都是空串，按钮显示「内测免费」且禁用；`docs/pay.md` 写了三步，没有注册任何支付账号。付款后解锁什么也没有做（纯静态页没有 license 校验），这是已知缺口。
5. **仓储侧一次返工**：`gh repo create --push` 推的是 `master`，Pages 建站报 `The main branch must exist before GitHub Pages can be built. (HTTP 422)`；改名 `main` 并 PATCH 默认分支后才建成。
