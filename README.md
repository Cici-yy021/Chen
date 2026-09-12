# 陈乔云 · 个人主页

一个零依赖的静态个人主页，直接部署在 GitHub Pages 上。

- `index.html` —— 整站，HTML + CSS + 少量 JS 全在这一个文件里，没有构建步骤
- `.nojekyll` —— 告诉 GitHub Pages 跳过 Jekyll 处理，加快构建

## 本地预览

双击 `index.html` 即可，或者起个本地服务器：

```bash
python3 -m http.server 8000
# 然后打开 http://localhost:8000
```

## 部署到 GitHub Pages

### 1. 在 GitHub 上新建仓库

打开 https://github.com/new ，仓库名填 **`personal-page`**（或任意名字），
**不要**勾选 "Add a README file"，创建后拿到仓库地址。

> 想让网址更短，可以把仓库名取成 `<你的用户名>.github.io`，
> 这样网址就是 `https://<你的用户名>.github.io/`（而不是带子路径的 `/personal-page/`）。

### 2. 推送代码

在本目录下执行（把 `<你的用户名>` 换成你的 GitHub 用户名）：

```bash
git remote add origin https://github.com/<你的用户名>/personal-page.git
git branch -M main
git push -u origin main
```

### 3. 开启 Pages

仓库页面 → **Settings** → 左侧 **Pages** →
**Source** 选 `Deploy from a branch`，**Branch** 选 `main` + `/ (root)`，**Save**。

等 1–2 分钟，访问：

```
https://<你的用户名>.github.io/personal-page/
```

### 4. 以后更新

改完文件后：

```bash
git add -A && git commit -m "更新内容" && git push
```

推送后 1 分钟左右自动重新发布。

## 发布前请检查

`index.html` 里还有几处占位/草稿内容，搜 `TODO` 就能定位：

- [ ] GitHub 链接还是 `yourname`，换成真实用户名（或删掉这一行）
- [ ] 「技能」里的标签是否和你的真实情况相符
- [ ] 「最近在做」的三张卡片是草稿，改成你真实在做的事
- [ ] 邮箱 `chenqiaoyun@example.com` 是示例地址，换成能收到信的邮箱
- [ ] 想放照片的话，把 `<div class="avatar">陈</div>` 换成 `<img src="avatar.jpg" alt="陈乔云">`，并把 `avatar.jpg` 放进本目录

## 换成自定义域名（可选）

1. 在仓库 Settings → Pages → Custom domain 填入域名，GitHub 会生成一个 `CNAME` 文件
2. 到你的域名服务商处添加 CNAME 记录指向 `<你的用户名>.github.io`
3. 勾选 Enforce HTTPS
