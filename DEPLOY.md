# 发布指南（三步上线 + 国内访问）

## 第一步：上传到 GitHub（国际主线，免费）

1. 注册/登录 [github.com](https://github.com)（免费）
2. 点右上角 + → New repository
   - 名称：如 `voice-3d`（随意，会出现在网址里）
   - 选 **Public**（公开）
   - 勾选 Add a README → Create repository
3. 上传文件：仓库页 → Add file → Upload files
   - 把 `release/` 里的**全部内容**拖进去：`index.html`、**`lib/` 文件夹**、`LICENSE`、`README.md`、`THIRD_PARTY_NOTICES.md`
   - **必须连 `lib/` 一起上传。** 页面里没有任何 CDN 兜底，3D 引擎只从本地的 `lib/` 加载；缺了 `lib/`，3D 区一定打不开（文字、题库仍可用）。
   - `lib/` 里文件多，网页上传慢可以分几次传、慢慢补齐，但**一个文件都不能少**。
   - Commit changes

## 第二步：开启 GitHub Pages（获得公开网址）

1. 仓库页 → Settings → Pages（左侧栏）
2. Source 选 `Deploy from a branch`，Branch 选 `main`，目录选 `/ (root)` → Save
3. 等 1-2 分钟，刷新后页面顶部出现网址：
   `https://你的用户名.github.io/voice-3d/`
   这个地址自带 HTTPS，在 GitHub Pages 的免费额度内不额外收费（具体政策以平台现行条款为准；公开仓库的静态站点通常免费，但别把它当成「永不花钱」的承诺）。

## 第三步：国内访问（两招，可都做）

### 招一：Gitee 镜像（国内主力，速度快）

1. 注册/登录 [gitee.com](https://gitee.com)（需实名认证一次）
2. 新建仓库 → 点「导入已有仓库」→ 粘贴你的 GitHub 仓库网址 → 一键导入
   （以后 GitHub 更新后，Gitee 仓库点一下「同步」即可）
3. Gitee 仓库 → 服务 → Gitee Pages → 开通（需实名审核，通常当天过）
   得到国内访问链接 `https://你的gitee用户名.gitee.io/voice-3d/`
   同样要确认**仓库里带着 `lib/`**，否则 3D 出不来。

### 招二：jsDelivr CDN 直链（免审核备用）

GitHub 仓库公开后，可以试这个直链：

```
https://cdn.jsdelivr.net/gh/你的用户名/voice-3d/index.html
```

几点提醒（**这条入口本稿未实测**，上线前请自己点开确认）：

- 相对路径 `./lib/...` 是否能被正确解析，取决于 jsDelivr 当次的仓库分发行为，**必须打开页面看到 3D 模型能转**才算可用；
- 该入口只适合当备用，别作为分享文案里的主链接；
- 若打开后 3D 区显示加载失败，说明 `lib/` 没被正确带出，改用 Gitee Pages 或 GitHub Pages。

## 日常更新

改了文件后：GitHub 仓库 → Add file → Upload files 覆盖上传（`index.html` 和 `lib/` 里改过的文件都要重传）→ Gitee 点同步。两端就都更新了。
只改文案（页脚、关于弹窗）时，也建议顺手核一遍 `LICENSE`、`THIRD_PARTY_NOTICES.md`、`README.md` 的署名口径是否一致。

## 发布前自检（5 分钟）

1. 用线上地址打开页面 → 3D 模型能转动、能点结构出知识卡；
2. 按 F12 看控制台：没有红色报错；不该出现 404（尤其 `lib/three@0.160.0/...`）；
3. 点页脚「关于」：数据许可那段与 `LICENSE` 第二部分说法一致；
4. 页脚能看到 BodyParts3D 署名与 CC BY-SA 链接，并确认没有给数据添加「仅供教学」这类用途限制；
5. 手机打开一次，确认能转、能答题。

## 常见问题

- **打开白屏 / 3D 区一片空白？** 九成是 `lib/` 没传全。核对仓库里是否存在 `lib/three@0.160.0/build/three.module.js`，以及 `lib/three@0.160.0/examples/jsm/` 下两个 addon 文件。
- **本地双击 `index.html` 打不开 3D？** 正常，浏览器拦截了 ES 模块。按 `README.md`「方式二」起个本地静态服务器再看。
- **GitHub 访问慢？** 那是给维护者用的，学生走 Gitee / jsDelivr 链接。
- **想改标题/署名？** 直接编辑 `index.html` 里的文字，但**不要删掉页脚的 BodyParts3D 署名与许可链接**，也不要删 `LICENSE`、`THIRD_PARTY_NOTICES.md`；`lib/` 更不能删。
