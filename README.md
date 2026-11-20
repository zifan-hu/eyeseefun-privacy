# EYE SEE FUN — 隐私权政策发布说明

`index.html` 已经是最终页面（单文件，无外部依赖、无 CDN、无 JS），只要放到任意
公网 HTTPS 地址上就能用。

---

## 一、三条上线路线（按省事程度排序）

### 路线 A：Netlify Drop（最快，免注册，1 分钟）

1. 浏览器打开 https://app.netlify.com/drop
2. 把整个 `eyeseefun-privacy` 文件夹拖进页面中央
3. 等 5–10 秒，页面会给出一个形如
   `https://sparkly-panda-1a2b3c.netlify.app` 的地址
4. 这个地址就是隐私权政策网址 —— 直接粘进 Play 控制台
5. （可选）注册一个免费账号把站点「认领」下来，避免日后丢失管理权

> 优点：不用装任何东西、不用命令行。缺点：随机域名，看着不正式。

---

### 路线 B：GitHub Pages（永久、免费、URL 干净）

需要 GitHub 账号，命令行方式：

```bash
cd /Users/a1/Documents/deepseek-harness/default-workspace/eyeseefun-privacy

git init
git add index.html
git commit -m "Add privacy policy for EYE SEE FUN"
git branch -M main
git remote add origin https://github.com/<你的用户名>/eyeseefun-privacy.git
git push -u origin main
```

然后在仓库页面：**Settings → Pages → Source 选 `Deploy from a branch` → Branch 选 `main` / `(root)` → Save**。
约 1 分钟后地址生效：

```
https://<你的用户名>.github.io/eyeseefun-privacy/
```

> 优点：永久免费、URL 体面、可长期维护。缺点：要先建仓库、装 git。

---

### 路线 C：Google Sites（最傻瓜，5 分钟，你已登录 Google 账号）

1. 打开 https://sites.google.com/new
2. 新建空白站点 → 标题填 `EYE SEE FUN Privacy Policy`
3. 正文区域粘贴 `index.html` 里「English」那段的文字（Google Sites 不吃 HTML 源码，
   只能粘可见文本，格式会略简）
4. 右上角「发布」→ 网址填 `eyeseefun-privacy` → 权限选「所有人」→ 发布
5. 得到 `https://sites.google.com/view/eyeseefun-privacy`

> 优点：图形界面，不用碰代码。缺点：要重新排版，URL 较长。

---

## 二、上线后自检（很重要，Google 会按这几条审）

用**无痕窗口**打开网址，确认：

- [ ] 地址是 `https://` 开头，浏览器地址栏没有「不安全」警告
- [ ] 不用登录、不用翻墙、不用点任何按钮就能看到全文
- [ ] 是普通网页，不是 PDF、不是 Google Docs/网盘预览页
- [ ] 页面上能看到应用名 **EYE SEE FUN** 和联系邮箱
- [ ] 手机打开排版也正常

任何一条不满足，Google 都可能判为无效并导致审核延迟。

---

## 三、容易被忽略的一条要求

Google 写的是：「您必须在**商品详情中**和**应用内**提供隐私权政策链接」——
即游戏内部也要有一个入口（设置页 / 关于页里放一条可点击的链接）。

如果控制台这一栏填了网址但应用内没有入口，审核可能因此被拒。建议在游戏的
「设置 → 关于」里加一行 `Privacy Policy`，点击用 `Intent.ACTION_VIEW` 打开
上面的网址。

---

## 四、需要你确认的假设

本页面是按「**纯离线、不收集任何数据**」写的，依据是 AAB 的权限清单里只有
`com.android.vending.CHECK_LICENSE`，没有 `INTERNET`。

如果你实际上：

- 接了广告（AdMob / Unity Ads / AppLovin 等）
- 接了统计（Firebase Analytics / Unity Analytics / 友盟等）
- 用了 Google Play 游戏服务（登录、排行榜、成就）
- 有内购以外的任何联网行为
- 收集了崩溃日志并上传

那么必须改写「二、我们收集的信息」和「五、共享与披露」两节，否则与
**数据安全**表单不一致，会被判违规。需要的话告诉我接的是哪几家 SDK，
我按真实情况重写。
