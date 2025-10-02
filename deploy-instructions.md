# 📱 GitHub Pages 部署指南

## 🎯 当前状态
✅ 所有文件已准备完成！

## 📁 部署文件清单
- `index.html` - 主安装页面（自动检测设备类型）
- `iosApp.ipa` - iOS应用文件 (~15MB)
- `畅指动画demo.apk` - Android应用文件 (~10MB)
- `README.md` - 项目说明文档

## 🚀 部署步骤

### 1️⃣ 创建GitHub仓库
1. 访问 [GitHub](https://github.com)
2. 点击右上角 "+" → "New repository"
3. 填写信息：
   - **Repository name**: `ios-app-distribution` (或你喜欢的名字)
   - **Description**: `畅指动画 - iOS/Android 应用分发`
   - **Visibility**: ✅ Public (必须是公开的)
   - **Initialize**: ❌ 不要勾选任何初始化选项
4. 点击 "Create repository"

### 2️⃣ 上传文件到GitHub
有两种方式：

#### 方式A: 网页上传（推荐）
1. 在新创建的仓库页面，点击 "uploading an existing file"
2. 将这个文件夹中的所有文件拖拽到页面上：
   - `index.html`
   - `iosApp.ipa`
   - `畅指动画demo.apk`
   - `README.md`
3. 在底部填写提交信息：
   - **Commit title**: `Initial commit - iOS/Android app distribution`
   - **Description**: `添加应用分发页面和安装文件`
4. 点击 "Commit changes"

#### 方式B: 命令行上传
```bash
cd github-pages-deploy
git init
git add .
git commit -m "Initial commit - iOS/Android app distribution"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git push -u origin main
```

### 3️⃣ 启用GitHub Pages
1. 进入仓库页面
2. 点击 "Settings" 标签
3. 在左侧菜单中找到 "Pages"
4. 在 "Source" 部分：
   - 选择 "Deploy from a branch"
   - Branch: 选择 "main"
   - Folder: 选择 "/ (root)"
5. 点击 "Save"

### 4️⃣ 获取访问链接
几分钟后，GitHub会提供访问链接：
```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

### 5️⃣ 生成最终二维码
将下面的代码中的链接替换为你的实际链接，然后运行：

```python
import qrcode

# 替换为你的实际GitHub Pages链接
url = "https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/"

qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_L,
    box_size=10,
    border=4,
)
qr.add_data(url)
qr.make(fit=True)

img = qr.make_image(fill_color='black', back_color='white')
img.save('final-qrcode.png')
print(f'✅ 最终二维码已生成: final-qrcode.png')
print(f'🌐 链接: {url}')
```

## 🎉 完成！
- ✅ 任何人都可以扫码或访问链接
- ✅ 自动检测iOS/Android设备
- ✅ 无需VPN或特殊网络配置
- ✅ 全球可访问，永久有效

## 📱 用户使用流程
1. 扫描二维码或访问链接
2. 页面自动检测设备类型
3. iOS用户看到IPA下载，Android用户看到APK下载
4. 点击下载按钮即可获取应用文件

## ⚠️ 注意事项
- GitHub Pages有流量限制（100GB/月）
- 文件大小限制（100MB/文件）
- 部署可能需要几分钟生效
- 确保仓库是Public的

---
**需要帮助？** 如有问题请联系开发者！
