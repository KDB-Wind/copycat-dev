# p4 图片压缩到指定 KB（报名照片）

- URL: https://kdb-wind.github.io/copycat-dev/p4/
- 人群：要上传证件照的考生 / 职称评审 / 事业单位报名 / 签证与护照申请的人
- 需求类型：**事件驱动**——只有报名窗口那几天有量，过后归零
- 一句话卖点：不只压缩，还告诉你「实际 96KB、295×413px、符合这条规格」

## 中文帖子（可直接复制）

### 1) 小红书 · 口吻：刚被系统拒过

> 报名系统提示「照片不能超过 100KB」，我拿原图压了三次都没过，最后一次直接糊了。
> 后来才知道顺序错了：**先缩尺寸再降质量**。一张 4000×3000 的手机照片，先缩到 295×413，再压质量，出来 40 多 KB，人脸细节还在。
> 反过来先降质量、尺寸不动，出来的图在小窗口里浑身是块。
> 还有个坑：把 .png 改成 .jpg 不算压缩，一个字节都没少。

### 2) B站评论区 · 口吻：给正在报名的人

> 顺手说一下证件照怎么压不糊：先定尺寸（一寸 295×413、二寸 413×579），再降 JPEG 质量，别反过来。
> 手机相册里直接「编辑→分辨率」也能改，但不会帮你算到 KB 以下；网页版一般会二分试质量。
> 注意看输出是不是真的 295×413，有的工具只压体积不改尺寸，上传还是被拒。

### 3) 知乎回答 · 口吻：回答「报名照片怎么压到 100KB 以内」

> 关键不是「压」，是**先定尺寸、再定质量**。
> ① 先确认系统要的像素：多数人事考试要一寸（295×413）或二寸（413×579），不是「随便小于 100KB」就行。尺寸不对，体积再小也会被拒。
> ② 按目标尺寸裁切（证件照居中偏上，别把头顶切掉），再降 JPEG 质量，一般 0.7–0.85 就能进 100KB。
> ③ 压完看两个数：实际 KB 和实际像素。只看第一个数的人，经常第二次还是被拒。
> 顺手做的工具在这儿，本地处理、照片不上传：https://kdb-wind.github.io/copycat-dev/p4/

## 英文帖子 ×2

### r/techsupport

> Title: Application portal says "photo must be under 100KB" — resize first, compress second
>
> The order matters. If you only lower JPEG quality on a 4000×3000 phone photo, you get blocky artifacts and often still miss the limit. Resize to the pixel dimensions the form asks for (often 295×413 or 2×2 inch at 300dpi), then lower quality — a normal portrait lands at 40–90KB with the face intact.
>
> Also: renaming `.png` to `.jpg` changes nothing; the bytes stay the same. And if the form wants a specific pixel size, check the output width, not just the KB.
>
> I made a browser-only page that does exactly this and prints the verdict (actual KB + actual pixels vs the preset): https://kdb-wind.github.io/copycat-dev/p4/

### r/immigration

> Title: Passport/visa photo uploads: check pixels before KB
>
> Most rejections I see are dimension failures, not size failures — people compress to 80KB but leave the image at 3000px wide. Fix the pixel grid first (e.g. 600×600 for a US-style square photo, 390×567 for a 33×48mm passport shot), then compress.
>
> For the compression step, a browser tool is enough and avoids uploading your passport photo to a random server: https://kdb-wind.github.io/copycat-dev/p4/

## 目标社区（具体）

- 知乎：问题「报名照片怎么压缩到100kb」「证件照尺寸怎么改」；话题「公务员考试」「事业单位招聘」「证件照」
- 小红书：话题标签 `#报名照片` `#证件照` `#照片压缩` `#京考` `#事业单位报名`
- B站：搜「报名照片压缩」「证件照换底色」的教程视频，只在评论区补充
- Reddit：`r/techsupport`、`r/immigration`、`r/Passports`（这三个版对 self-promo 相对宽松，但仍要求先回答问题）
- 贴吧：`公务员考试吧`、`事业单位吧` 的报名季置顶帖下面

## 时间窗

- **纯事件驱动**：国考（10 月报名）、省考（1–3 月）、事业单位联考（4–5 月）、职称评审（各地不同）。
- 最佳发帖时间：报名公告发布后 **24–48 小时内**，那时候贴吧和知乎的问题量最大。
- 平时发＝没人看，别浪费账号权重；淡季只做一件事：把知乎那几个常青问题回答好，等报名季自然来流量。

## 硬规则（每份都照做）

1. 同一账号、同一平台，**每天只发一条**。
2. **先回答别人的问题，再谈自己的工具**；报名季问题多，先答三个再考虑提一次自己的。
3. 不许开小号、不许群发、不许在同一个帖子下重复贴链接。
4. 不许在帖子里承诺「一定过审」——各系统口径不同，你没这个资格。
