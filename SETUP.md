# 快速设置指南

## 第一步：创建数据仓库

1. 访问 https://github.com/new
2. 仓库名称：`MyAccountingData`
3. 选择 **Public** 或 **Private**
4. 勾选 "Add a README file"
5. 点击 "Create repository"

## 第二步：获取 GitHub Token

1. 访问 https://github.com/settings/tokens/new
2. Token 名称：`Accounting App`
3. 勾选权限：✅ **repo** (Full control of private repositories)
4. 点击 "Generate token" (绿色按钮)
5. **复制 token**（格式：`ghp_xxxxxxxxxxxx`）

⚠️ **重要**：Token 只显示一次，请妥善保存！

## 第三步：部署应用到 GitHub Pages

### 3.1 创建应用仓库

1. 访问 https://github.com/new
2. 仓库名称：`MyAccountingWeb`
3. 选择 **Public**（GitHub Pages 免费版需要公开仓库）
4. **不要**勾选 "Add a README file"
5. 点击 "Create repository"

### 3.2 上传代码（选择一种方式）

#### 方式 A：通过网页上传

1. 在新创建的 `MyAccountingWeb` 仓库页面
2. 点击 "uploading an existing file"
3. 拖拽或选择 `index.html` 文件
4. 在 "Commit changes" 输入：`Initial commit`
5. 点击 "Commit changes"

#### 方式 B：通过命令行

```bash
cd /e/VScodeProjects/MyAccountingWeb
git remote add origin https://github.com/你的用户名/MyAccountingWeb.git
git branch -M main
git push -u origin main
```

### 3.3 启用 GitHub Pages

1. 进入仓库 **Settings**（设置）
2. 左侧菜单点击 **Pages**
3. 在 **Source** 部分：
   - Branch: 选择 `main`
   - Folder: 选择 `/ (root)`
4. 点击 **Save**

等待 1-2 分钟，刷新页面，顶部会显示：
```
Your site is live at https://你的用户名.github.io/MyAccountingWeb/
```

## 第四步：配置应用

1. 打开你的应用地址（如：https://你的用户名.github.io/MyAccountingWeb/）

2. 点击 **"⚙️ GitHub 配置"** 展开配置表单

3. 填写信息：
   ```
   GitHub 用户名:    你的用户名（如：zz-nan）
   仓库名称:         MyAccountingData
   Personal Access Token:  ghp_xxxxxxxxxxxx（粘贴刚才复制的）
   Excel 文件路径:    data/收支账单.xlsx（保持默认）
   ```

4. 点击 **"保存配置"**

5. 点击 **"测试连接"** - 应该显示 "连接成功！"

6. 点击 **"从 GitHub 加载"** - 首次会自动创建 Excel 文件

## 第五步：开始使用

现在你可以：
- ✅ 添加、编辑、删除账单
- ✅ 查看月度统计分析
- ✅ 点击 "🔄 同步到 GitHub" 手动同步

## 访问你的数据

任何时候都可以在 GitHub 仓库中查看 Excel 文件：
```
https://github.com/你的用户名/MyAccountingData/blob/main/data/收支账单.xlsx
```

## 多设备使用

在其他设备上：
1. 访问 https://你的用户名.github.io/MyAccountingWeb/
2. 填写相同的 GitHub 配置信息
3. 点击 "从 GitHub 加载"
4. 开始使用

## 常见问题

### Q: "测试连接" 失败
A: 检查：
- 用户名和仓库名是否正确
- Token 是否正确（以 `ghp_` 开头）
- Token 是否有 repo 权限
- 仓库是否存在

### Q: GitHub Pages 显示 404
A:
- 等待 2-3 分钟刷新
- 确认仓库名拼写正确
- 检查 Pages 设置中的分支是否为 main

### Q: 配置丢失
A: 配置保存在浏览器中，清除浏览器数据会丢失。重新配置即可。

## 安全建议

1. **使用私有仓库**：如果你有 GitHub 付费账号，建议将数据仓库设为 Private
2. **定期更换 Token**：每隔几个月更换一次 GitHub Token
3. **备份数据**：定期从 GitHub 仓库下载 Excel 文件备份

## 技术支持

如有问题，请查看 README.md 或提交 Issue。
