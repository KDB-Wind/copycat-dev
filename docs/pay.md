# 收款位怎么接（三步，今晚没做）

三个页面底部都有一行：

```js
const BUY_URL = ""; // 留空 = 内测免费
```

留空时按钮显示「内测免费」且不可点。填上链接后按钮变成「买断 · $N」，点击在新标签打开 checkout。

## 1. 在 Lemon Squeezy 建产品

1. 注册 Lemon Squeezy（需要实名/税务信息，账号持有人自己填）。
2. Store → Products → New product：类型选 **Digital product / 一次性买断**，价格自己定。
3. 把 Product 的 **Checkout link** 复制下来（形如 `https://你的店.lemonsqueezy.com/buy/<uuid>`）。

## 2. 把链接填进对应的常量

- `p1/index.html`：搜 `const BUY_URL = "";`
- `p2/index.html`
- `p3/index.html`

例如：

```js
const BUY_URL = "https://yourstore.lemonsqueezy.com/buy/xxxxxxxx-xxxx";
```

同时把按钮文字里的价格改成实际价格（`买断 · $9` / `$12` / `$9` 是占位）。

## 3. push

```
git add -A
git commit -m "add checkout link"
git push
```

Pages 1–2 分钟后生效。验证：打开页面 → 底部按钮不再是「内测免费」→ 点开是新标签里的 checkout 页。

## 边界

- 不要在这里填任何收款账号、银行卡、KYC 资料。
- 现在是纯静态页，没有 license 校验：付款后解锁什么，需要另加（例如付款邮件里发一个带参数的链接）。今晚没做，属于已知缺口。
