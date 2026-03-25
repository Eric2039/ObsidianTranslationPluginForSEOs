# DeepSeek Translator for Obsidian

在 Obsidian 中一键调用 DeepSeek API，将选中的英文内容翻译为中文，结果直接写回笔记。

---

## 功能特性

- 选中文字后翻译，未选中则翻译整篇笔记
- 三种输出模式：替换原文 / 追加在下方 / 新建笔记
- 支持命令面板（`Ctrl+P`）和编辑器右键菜单两种触发方式
- 内置 SEO 翻译 Prompt，保留 Markdown 格式
- 翻译中显示 loading 提示，出错有明确错误信息

---

## 安装

### 方式一：直接使用（推荐）

1. 下载 `main.js` 和 `manifest.json` 两个文件
2. 在你的 Obsidian vault 目录下创建文件夹：
   ```
   <你的vault>/.obsidian/plugins/obsidian-deepseek-translator/
   ```
3. 将两个文件放入该文件夹
4. 打开 Obsidian → **设置** → **第三方插件**
5. 关闭「安全模式」→ 点击刷新 → 启用 **DeepSeek Translator**

### 方式二：从源码构建（开发者）

```bash
git clone <仓库地址>
cd ObsidianSEOplugin
npm install
npm run build
```

构建完成后，将 `main.js` 和 `manifest.json` 按方式一安装。

---

## 使用方法

**命令面板：**
1. 在笔记中选中英文（或不选中以翻译全文）
2. `Ctrl+P` 打开命令面板
3. 搜索并执行「翻译为中文」

**右键菜单：**
1. 选中一段英文
2. 右键 → 点击「翻译为中文」

---

## 插件设置

打开 Obsidian → **设置** → **DeepSeek Translator**

| 设置项 | 说明 |
|--------|------|
| **DeepSeek API Key** | 你的 API Key，格式为 `sk-...` |
| **输出模式** | 替换原文 / 追加在下方 / 新建笔记 |
| **系统 Prompt** | 发送给 AI 的翻译指令，预填了 SEO 翻译模板，可自定义 |
| **Temperature** | 输出随机性（0~1），翻译建议保持默认值 0.3 |

---

## 获取 DeepSeek API Key

1. 访问 [platform.deepseek.com](https://platform.deepseek.com)
2. 注册 / 登录账号
3. 进入「API Keys」页面，点击「创建 API Key」
4. 复制生成的 Key（格式为 `sk-...`），粘贴到插件设置中

> **注意**：API Key 具有费用，请妥善保管，不要分享给他人。

---

## 常见错误

| 错误提示 | 原因 | 解决方法 |
|----------|------|----------|
| API Key 无效 | Key 填写错误或已失效 | 检查设置中的 API Key |
| API 账户余额不足 | DeepSeek 账户余额用完 | 登录平台充值 |
| 请求过于频繁 | 短时间内请求次数过多 | 稍等片刻后重试 |
| 网络连接超时 | 网络问题 | 检查网络连接后重试 |
