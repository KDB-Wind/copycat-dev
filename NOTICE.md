# NOTICE — 第三方代码与来源

本仓库不是纯原创代码库：`p6/index.html` 里内联了一个第三方二维码编码库。按 MIT 的要求，声明如下。

## 1. qrcode-generator

- 用在哪：`p6/index.html`（二维码生成器）内的 `<script>` 中、`/* qrcode-generator (MIT...` 注释之后
- 项目：https://github.com/kazuhikoarase/qrcode-generator
- 作者：Kazuhiko Arase
- 许可证：MIT（原文见本仓库 `LICENSE-qrcode-generator.txt`，逐字复制自上游 `LICENSE`，未改一字）
- 取用文件：上游 `js/dist/qrcode.js`（master 分支，2026-11-27 取用）
- 改动：
  1. 原样内联进单页 HTML，**未修改任何编码算法**；
  2. 上游文件末尾的 AMD / CommonJS 包装保留着，在浏览器里不生效，也没删；
  3. 新增的只有外面那层界面、尺寸/容错/留白控件、PNG 与 SVG 导出、以及页面文案。
- 商标/署名：页脚保留了作者与项目链接。

## 2. 没有用到的

`p1` / `p2` / `p3` / `p4` / `p5` 全部是原生 JS 手写，没有引入任何第三方库、字体或图标集。

## 3. 如果要替换

`p6` 里第三方代码只负责 `qrcode(text)` → 模块矩阵这一件事，接口是：

```js
const qr = qrcode(0, 'M'); qr.addData(text); qr.make();
qr.getModuleCount(); qr.isDark(row, col);
```

想换别的 MIT 库（例如 soldair/node-qrcode），只要保持这四个方法，替换后重新验证「生成 / 下载 PNG / 下载 SVG」三件事即可。
