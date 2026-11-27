# copycat-dev

六个单页小工具，都是原生 HTML/CSS/JS、无构建、无后端。打开就能用，数据不出浏览器。

线上：https://kdb-wind.github.io/copycat-dev/

| 目录 | 是什么 | 给谁 |
|---|---|---|
| `p1/` | 文本整理器：中文标点、中英文间距、空行、引号成对、繁简转换、改动高亮、导出 .md | 从 Word / 微信 / PDF 复制文字出来发布的人 |
| `p2/` | 线索抽取器：从一段乱文本抽邮箱、电话、链接、金额，去重、导 CSV、规则可分享 | 抄联系人的销售 / 招聘 / BD |
| `p3/` | 资料卡：常用填表信息存本机，点一下复制，整卡导出导入 | 反复填报名表 / 寄件单 / 报销单的人 |
| `p4/` | 图片压缩：压到指定 KB，先缩尺寸再降质量 | 报名系统卡 100KB 上传失败的人 |
| `p5/` | 时区会议：一个时间看清各城市几点、在不在上班时间 | 约跨国会议的远程团队 / 外贸 |
| `p6/` | 二维码：静态码，PNG / SVG 导出，不注册不加水印 | 要印贴纸、海报、名片的店主与活动运营 |

## 第三方代码

`p6/index.html` 内联了 [kazuhikoarase/qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator)（MIT，Copyright © 2009 Kazuhiko Arase）。许可证原文在 `LICENSE-qrcode-generator.txt`，改动说明在 `NOTICE.md`。

**改了哪几处**：只内联，没改编码算法；新增的是外层界面、尺寸/容错/留白三个控件、PNG 与 SVG 导出函数、页面文案。上游文件末尾的 AMD/CommonJS 包装原样保留（浏览器下不生效）。

其余五个页面是手写原生 JS，零依赖。

## 本地怎么跑

直接双击 `index.html`，或任意静态服务器：

```
npx serve .
```

## 部署

GitHub Pages，`main` 分支根目录。每次改完：

```
git add -A && git commit -m "..." && git push
```

1–2 分钟生效。

## 已知边界

- 没有账号、没有后端、没有 license 校验：付款后解锁什么还没做，收款位是空的（`BUY_URL = ""`，显示「内测免费」）。接入步骤见 `docs/pay.md`。
- `p3` 数据只在本机 localStorage，清浏览器数据就没了，所以要提供 JSON 导出。
- `p4` 解不了 iPhone 的 HEIC，要用户先转 JPG。
- `p5` 依赖浏览器自带的时区库，各国临时取消夏令时的新闻可能滞后。
- `p1` 的繁简是常用字表（1076 对），干/台/里/只/面 这类多对一的字故意不转。
