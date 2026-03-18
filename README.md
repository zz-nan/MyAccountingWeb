# 个人记账系统 - GitHub Excel 同步版

一个纯前端的个人收支记账应用，数据存储在 GitHub 仓库的 Excel 文件中，支持跨设备访问。

## 功能特性

- ✅ **收支记录管理**：添加、编辑、删除账单记录
- ✅ **Excel 数据存储**：数据存储在 GitHub 仓库的 Excel 文件中
- ✅ **跨设备同步**：只要能访问 GitHub，就能访问你的记账数据
- ✅ **分类管理**：支持多种收入/支出分类
- ✅ **月度筛选**：按月份查看账单列表和统计
- ✅ **数据分析**：月度收支统计、支出分类占比图表
- ✅ **自动同步**：每次记账后可自动同步到 GitHub
- ✅ **响应式设计**：支持手机、平板、电脑访问

## 技术栈

- **HTML5** - 页面结构
- **Bootstrap 5** - UI 框架
- **ECharts** - 数据可视化
- **SheetJS (XLSX)** - Excel 文件处理
- **GitHub API** - 数据存储和同步
- **Vanilla JavaScript** - 业务逻辑

## 快速开始

### 1. 创建 GitHub 数据仓库

首先创建一个专门用于存储数据的 GitHub 仓库：

1. 访问 [GitHub](https://github.com) 并登录
2. 点击右上角 **+** → **New repository**
3. 仓库名称：`MyAccountingData`（或任意名称）
4. 选择 **Public** 或 **Private**（私有需要付费账号）
5. **勾选** "Add a README file"
6. 点击 **Create repository**

### 2. 获取 GitHub Personal Access Token

1. 访问 https://github.com/settings/tokens/new
2. 勾选权限：
   - ✅ **repo** (Full control of private repositories)
3. 点击 "Generate token"
4. **重要**：复制生成的 token（只显示一次！）
5. 妥善保存这个 token

### 3. 配置应用

1. 打开应用后，点击顶部的 **"⚙️ GitHub 配置"**
2. 填写信息：
   - **GitHub 用户名**：你的 GitHub 用户名（如：`zz-nan`）
   - **仓库名称**：数据仓库名（如：`MyAccountingData`）
   - **Personal Access Token**：粘贴刚才获取的 token
   - **Excel 文件路径**：`data/收支账单.xlsx`（默认）
3. 点击 **"保存配置"**
4. 点击 **"测试连接"** 确认配置正确
5. 点击 **"从 GitHub 加载"** 加载数据（首次使用会自动创建 Excel 文件）

### 4. 开始记账

配置完成后，就可以正常使用记账功能了：
- 添加、编辑、删除账单
- 点击 **"🔄 同步到 GitHub"** 按钮手动同步
- 每次操作后数据会自动保存到本地浏览器

## 部署到 GitHub Pages

### 方式一：直接部署（推荐）

1. 在 GitHub 上创建新仓库 `MyAccountingWeb`
2. 将 `index.html` 上传到仓库
3. 进入仓库 Settings → Pages
4. Source 选择 `Deploy from a branch`
5. Branch 选择 `main` 或 `master`，目录选择 `/ (root)`
6. 点击 Save
7. 等待几分钟后，访问 `https://你的用户名.github.io/MyAccountingWeb/`

### 方式二：命令行部署

```bash
# 克隆仓库
git clone https://github.com/你的用户名/MyAccountingWeb.git
cd MyAccountingWeb

# 复制 index.html 到仓库
cp /path/to/index.html .

# 提交并推送
git add index.html
git commit -m "Add accounting application"
git push origin main
```

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

## 数据结构

Excel 文件结构：

| 日期 | 类型 | 分类 | 金额 | 备注 |
|------|------|------|------|------|
| 2026-03-18 | 支出 | 餐饮 | 50.00 | 午餐 |
| 2026-03-18 | 收入 | 薪资 | 10000.00 | 三月工资 |

文件存储在 GitHub 仓库的 `data/收支账单.xlsx` 路径。

## 工作原理

```
┌─────────────┐
│  浏览器界面  │
└──────┬──────┘
       │
       ├─ 本地存储 (localStorage)
       │  └─ 快速访问，离线可用
       │
       └─ GitHub API
          └─ 读取/写入 Excel 文件
             └─ 持久化存储，跨设备同步
```

### 数据流程

1. **加载数据**：从 GitHub 读取 Excel 文件，解析后存储到 localStorage
2. **添加/编辑/删除**：更新 localStorage 中的数据
3. **同步到 GitHub**：将数据转换为 Excel 格式，通过 GitHub API 提交到仓库

## 安全说明

- **Token 安全**：
  - Token 存储在浏览器的 localStorage 中
  - 不要在公共电脑上使用
  - 定期更换 Token（可在 GitHub 设置中撤销）

- **数据隐私**：
  - 如果使用 Public 仓库，Excel 文件会被公开
  - 建议使用 Private 仓库（需要 GitHub 付费账号）
  - 或自行搭建 GitHub Server

## 常见问题

### Q: 数据会丢失吗？
A: 数据存储在两处：
1. 浏览器 localStorage（清除浏览器数据会丢失）
2. GitHub 仓库的 Excel 文件（持久保存）

建议定期检查 GitHub 仓库中的 Excel 文件。

### Q: 可以在多个设备上使用吗？
A: 可以！只要在每台设备上配置相同的 GitHub 仓库信息即可。

### Q: 如何备份数据？
A:
1. 数据已自动备份到 GitHub 仓库
2. 可以直接在 GitHub 上下载 Excel 文件
3. 或使用 "Export Excel" 功能（如果有）

### Q: GitHub API 有请求限制吗？
A: 有：
- 认证用户：每小时 5000 次请求
- 正常使用不会超限
- 如果超限，可以等待一小时后重试

### Q: 如何更新 Token？
A:
1. 访问 https://github.com/settings/tokens
2. 撤销旧 Token
3. 生成新 Token
4. 在应用配置中更新

## 进阶功能

### 自动同步
在浏览器控制台执行以下代码可启用自动同步：

```javascript
const config = JSON.parse(localStorage.getItem('github_config'));
config.autoSync = true;  // 每次操作后自动同步
config.autoLoad = true;  // 启动时自动加载
localStorage.setItem('github_config', JSON.stringify(config));
location.reload();
```

### 导出数据到本地 Excel

可以在 GitHub 仓库中直接下载 `data/收支账单.xlsx` 文件。

## 项目特点

- 🚀 **纯前端**：无需后端服务器
- 📊 **Excel 存储**：数据格式通用
- 🔄 **GitHub 同步**：跨设备访问
- 💾 **双重存储**：本地 + 云端
- 📱 **响应式**：支持各种设备
- 🎨 **界面美观**：现代化设计
- 🔒 **隐私保护**：使用私有仓库

## License

MIT

## 相关链接

- [GitHub Pages 文档](https://docs.github.com/pages)
- [GitHub Personal Access Tokens](https://github.com/settings/tokens)
- [SheetJS 文档](https://sheetjs.com/)
- [ECharts 文档](https://echarts.apache.org/)
