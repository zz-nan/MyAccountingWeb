# 个人记账系统 - 纯前端版本

一个基于纯前端技术的个人收支记账应用，所有数据存储在浏览器本地，无需后端服务器。

## 功能特性

- ✅ **收支记录管理**：添加、编辑、删除账单记录
- ✅ **分类管理**：支持多种收入/支出分类
- ✅ **月度筛选**：按月份查看账单列表和统计
- ✅ **数据分析**：月度收支统计、支出分类占比图表
- ✅ **数据导出**：支持导出数据为 JSON 文件备份
- ✅ **本地存储**：使用 localStorage 存储数据
- ✅ **响应式设计**：支持手机、平板、电脑访问

## 技术栈

- **HTML5** - 页面结构
- **Bootstrap 5** - UI 框架
- **ECharts** - 数据可视化
- **Vanilla JavaScript** - 业务逻辑
- **localStorage** - 数据存储

## 在线访问

部署到 GitHub Pages 后，可通过以下地址访问：
```
https://你的用户名.github.io/MyAccountingWeb/
```

## 本地运行

1. 克隆或下载项目
2. 直接在浏览器中打开 `index.html` 文件

或者使用本地服务器：

```bash
# 使用 Python
python -m http.server 8000

# 使用 Node.js
npx serve

# 访问 http://localhost:8000
```

## 数据存储

- 所有数据存储在浏览器的 localStorage 中
- 数据只在当前浏览器中有效，不会同步到其他设备
- 建议定期使用"导出数据"功能备份数据

## 分类说明

### 收入分类
- 薪资
- 投资收益
- 其他

### 支出分类
- 房租
- 房贷
- 餐饮
- 交通
- 日用品
- 水电燃气
- 购物
- 汽车
- 医疗
- 其他

## 部署到 GitHub Pages

### 方法一：通过 GitHub 网页界面

1. 在 GitHub 上创建新仓库 `MyAccountingWeb`
2. 上传 `index.html` 文件到仓库
3. 进入仓库 Settings → Pages
4. 在 Source 下选择 `Deploy from a branch`
5. 选择分支（通常是 `main` 或 `master`）和 `/ (root)` 目录
6. 点击 Save
7. 等待几分钟后，访问 `https://你的用户名.github.io/MyAccountingWeb/`

### 方法二：通过命令行

```bash
# 初始化 git 仓库
git init

# 添加文件
git add index.html
git commit -m "Initial commit"

# 添加远程仓库
git remote add origin https://github.com/你的用户名/MyAccountingWeb.git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

然后在 GitHub 仓库设置中启用 GitHub Pages。

## 数据备份与恢复

### 备份数据
点击页面顶部的"导出数据"按钮，将下载一个 JSON 文件。

### 恢复数据（需手动修改代码）
如果需要恢复数据，可以在浏览器控制台执行：

```javascript
// 读取备份文件
const data = {...}; // 从导出的 JSON 文件中复制
localStorage.setItem('my_accounting_data', JSON.stringify(data));
location.reload();
```

## 隐私说明

- 所有数据仅存储在您的浏览器本地，不会上传到任何服务器
- 清除浏览器数据会导致记账数据丢失
- 建议定期导出备份

## 项目特点

- 🚀 **零后端**：无需服务器，部署简单
- 📱 **响应式**：支持各种设备
- 💾 **本地存储**：数据隐私安全
- 🎨 **界面美观**：现代化的 UI 设计
- 📊 **数据可视化**：ECharts 图表展示

## License

MIT
