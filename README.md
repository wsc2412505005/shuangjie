# 双节同庆祝福页面

倒计时粒子开场 → 自动播放背景音乐 → 金色代码雨祝福成语 + 烟花 + 卡通百人合影。

## 本地预览

直接双击 `index.html`，或：

```bash
npx serve -p 8080 .
```

## 更换背景音乐

1. 将新 MP3 覆盖 `audio/bgm.mp3`
2. 修改 `index.html` 中音频源的版本号 `audio/bgm.mp3?v=YYYYMMDD`（防手机浏览器缓存旧文件）
3. 提交并推送，约 1 分钟后线上自动更新

## 部署说明（GitHub Pages）

首次部署步骤：

1. 在 GitHub 新建仓库（如 `shuangjie`），推送代码：
   ```bash
   git remote add origin https://github.com/<用户名>/shuangjie.git
   git push -u origin main
   ```
2. 仓库 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**
3. 推送即触发 `.github/workflows/deploy.yml` 自动部署

### 自定义域名

1. **将 `CNAME` 文件中的占位域名替换为你的实际域名**
2. 在域名 DNS 服务商添加解析记录：
   - 顶级域名：A 记录指向 GitHub Pages IP（以 GitHub 官方文档为准）
   - 子域名（如 `www.xxx.com`）：CNAME 记录指向 `<用户名>.github.io`
3. 仓库 **Settings → Pages → Custom domain** 填入域名并保存
4. 勾选 **Enforce HTTPS** 强制 HTTPS（证书签发需几分钟，DNS 生效后才可勾选）

### 路径说明

站内所有资源均为相对路径（`audio/bgm.mp3` 等），无论部署到仓库根、子路径还是自定义域名均可正常加载。

## 文件结构

```
index.html              页面与全部逻辑（Canvas 粒子/烟花/音乐控制）
audio/bgm.mp3           背景音乐
CNAME                   自定义域名（需替换占位内容）
.github/workflows/      GitHub Pages 自动部署工作流
```
