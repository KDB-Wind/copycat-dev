模型: opencode-go/deepseek-v4.1-flash

R2 交付：P1 按你的清单升级完（繁简 / 引号成对 / 导出 .md），三个新品 P4/P5/P6 全部上线，七个 URL 都是 200。

P1 tidytext（升级） | 状态: 已上线 | URL: https://kdb-wind.github.io/copycat-dev/p1/
  一句话: 给从 Word / 微信 / PDF 复制文字的人，一次理顺标点间距，并能看见改了哪里。
  数据: R1 的 `ios_6764243413`（文本工具箱）；本轮未再查 MCP
  自检: 5/5。新增三项都实测：繁→简「這是繁體中文，時間不夠」→「这是繁体中文，时间不够」；简→繁反向也对；引号「"引号"」→「“引号”」而 English "keep" 不动；导出 .md 触发下载；有任何一条规则时输出区用黄底/划线标出改动，可一键切回成稿
  下一步: 该加码——「繁简」和「引号」这两个词在搜的人比前三个功能多，但页面文案还没围绕它们写

P4 imgpress（图片压缩到指定 KB） | 状态: 已上线 | URL: https://kdb-wind.github.io/copycat-dev/p4/
  一句话: 给报名系统卡在 100KB 上传失败的人，把照片压到指定大小、不糊、不上传。
  数据: 非 stringer；搜索证据见本期 `## 需求证据`（百度文档页 / Reddit / B站 京考视频）
  自检: 5/5。①拖拽区 + 文件选择 + 目标 KB + 格式 ②415KB/2400×1800 的样例 → 99KB 达标，1024×768，质量 0.81，978ms ③下载按钮导出 PNG 并提示「已开始下载」 ④scrollWidth=375（docs/shots/p4-375.png）⑤console/errors 空
  下一步: 该加码——加「批量 + 证件照比例裁剪」就能吃到一整类报名场景；单张现在只是够用

P5 tzmeet（跨国会议时间） | 状态: 已上线 | URL: https://kdb-wind.github.io/copycat-dev/p5/
  一句话: 给约跨国会议的远程团队 / 外贸，填一个时间看清各城市几点、对方在不在上班。
  数据: 非 stringer；搜索证据见 `## 需求证据`（AMZ123 / TimeBie / 拓扑兔）
  自检: 5/5。①时间 + 时区 + 15 个城市开关 ②北京 2026-07-15 21:00 → 纽约 09:00（上班）、伦敦 14:00、洛杉矶 06:00；冬令时同场景北京 21:00 → 纽约 08:00；夏令时边界 `2026-03-08 01:30 → 06:30Z`、`03:30 → 07:30Z` 都对 ③「复制成会议通知」提示已复制，输出带日期、星期、次日标注 ④scrollWidth=375（docs/shots/p5-375.png）⑤console/errors 空
  下一步: 该加码——「复制成会议通知」是唯一有传播性的动作，可以做成一条可分享链接

P6 qrstatic（二维码） | 状态: 已上线 | URL: https://kdb-wind.github.io/copycat-dev/p6/
  一句话: 给要印海报 / 贴纸 / 名片的店主与活动运营，静态码、不注册、不加水印。
  数据: 非 stringer；搜索证据见 `## 需求证据`（ME-QR 博客 / Proton / GenQRCode）
  自检: 5/5。①文本框 + 尺寸/容错/留白三个控件 ②`https://kdb-wind.github.io/copycat-dev/` → 29×29 模块，导出 999×999px，画布渲染正常 ③下载 PNG（toBlob）与 SVG（矢量，印刷用）都能触发 ④scrollWidth=375（docs/shots/p6-375.png）⑤console/errors 空
  下一步: 小改——能扫、能印就够；下一步只补「打印尺寸换算 cm」，别再堆样式

## 需求证据

三条都在 2026-11-27 现查，逐条给可点的出处。**P6 那条是竞品页推断，不是用户原话，我标出来了。**

1. **图片压缩到指定 KB** — 搜索词 `图片压缩到100kb`、`照片压缩到指定大小kb`、`报名照片太大上传失败`
   - https://kuku.baidu.com/landing/tscp_doc/e0737be4c8a493b65858335278005119 —「报名考试、职称评审：上传证件照的系统常限制在200KB或100KB以内」
   - https://www.reddit.com/r/techsupport/comments/wd0b34/need_to_submit_a_100kb_photo — 英文区同一个问题
   - https://www.bilibili.com/video/BV16wWd6QEYL —「2027京考 报名照片太大上传失败…压缩到35kb到100kb之间」
   - 谁在搜：要上传证件照的考生，截止前才发现传不上去。

2. **跨国会议时区** — 搜索词 `美东时间 北京时间 换算`、`跨国会议 时差 怎么算`
   - https://m.amz123.com/ask/UjAd6KsG — 跨境电商导航站专门做这一问，全文在解释夏令时 12 小时 / 冬令时 13 小时
   - https://www.timebie.com/cn/easternbeijing.php — 只做「北京↔美东」一对，能长期存在说明配对搜索稳定
   - https://tools.top/timezone.html — 场景第一句是「商务协作：安排跨国会议」
   - 谁在搜：外贸 / 跨境运营 / 远程团队，搜的不是时区表，是「我这个会对方几点」。

3. **二维码免注册** — 搜索词 `免费二维码生成器 不用注册`、`二维码 不加水印`
   - https://me-qr.com/zh/page/blog/best-free-qr-code-generators-no-sign-required — 整篇博客标题就是「无需注册」，把免注册当独立卖点
   - https://proton.me/zh/pass/qr-code-generator — 主打「无广告、无跟踪、无需账户」
   - https://genqrcode.com/cn — 反复强调「绝不会包含广告」「静态码没有过期日期」
   - 谁在搜：要印海报 / 贴纸 / 门店码的店主。**注意：这是从竞品都在强调这几个词倒推的搜索意图，没有拿到关键词量，也没有用户原话，属于三条里最弱的一条。**

## 开源库这条硬规矩（今晚唯一没验证过的假设）

- 用的是 [kazuhikoarase/qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator)，取的是 `js/dist/qrcode.js`。
- **读了 LICENSE 原文**（不是看徽章）：`MIT License / Copyright (c) 2009 Kazuhiko Arase / Permission is hereby granted, free of charge...`，逐字存进仓库根 `LICENSE-qrcode-generator.txt`。
- 仓库根有 `NOTICE.md`：写清用在哪、哪个文件、改动是什么（只内联，未改算法，AMD 包装原样保留）。
- `README.md` 里有一段「改了哪几处」，并且说明了想换库时只要保住 `qrcode/addData/make/getModuleCount/isDark` 五个方法。
- 页脚保留了作者署名和项目链接——MIT 要求保留版权与许可声明。
- 结论：这条路技术上成立，但**它只解决「不用从零写编码器」，不解决流量**；p6 能不能起量跟这个库无关。

## 卡在哪

1. **本轮抓到一个跨页面的真 bug，5 个页面里 4 个中招**：`.primary` 按钮悬停时，通用 `button:hover{background:#f7f4ee}` 的选择器优先级（0,1,1）压过了 `.primary`（0,1,0），于是深色底的按钮变成白底 + 白字，**鼠标一放上去按钮就"消失"**。已给 `.primary:hover` 补回背景与文字色，p2/p3/p4/p6 都改了，并用 `hover` 后读 computed style 复查（返回 `rgb(124,58,237)/白` 等正确值）。
2. **P5 的时区换算第一版是错的**：我按「迭代校正」写的算法把偏移量应用了两次，北京 21:00 被算成 05:00。改成「用墙上时间反推、每次用 `utcGuess - asUTC` 修正」后，用夏令时切换当天（`2026-03-08 01:30/03:30`）验证通过。
3. **繁简字表第一次写错了对齐**：字表是一整串两字一对，我在 `專专` 后面多打了一个「业」，导致后面**全部**错位一位（`這`→`这这`、`業`→null）。用「有没有简体字被当成 key」扫出来，修完是 1076 对；干/台/里/只/面 这类多对一的字故意不收，页面文案写明了这是常用字表、不是完整 OpenCC。
4. **P6 的构建不是纯手写**：`p6/index.html` 由 `p6/_shell.html` + 上游 `qrcode.js` 用 `.check/build-p6.js` 拼出来，脚本在 `.check/`（已 gitignore）。也就是说仓库里 `p6/index.html` 是产物，改的时候要改 `_shell.html` 再重跑——这个约定我写进了 README，但确实比别的页面多一步。
5. **仍有没做的**：支付位还是空串（`BUY_URL=""`，三页显示「内测免费」）；P4 不支持 HEIC；P6 没有动态码 / 扫码统计；三个新页面都只有文案，没有做过任何真实流量的验证。
