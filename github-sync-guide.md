# GitHub 数据同步使用指南

## 功能概述

通过 GitHub Gist 实现与对象之间的数据同步，完全异步、手动控制，不影响页面加载。

## 使用流程

### 第一步：获取 GitHub Token

1. 登录 GitHub 账号
2. 进入 Settings -> Developer settings -> Personal access tokens -> Tokens (classic)
3. 点击 "Generate new token (classic)"
4. 勾选 `gist` 权限
5. 生成并复制 Token（注意：Token 只显示一次，请妥善保存）

### 第二步：在页面中配置 Token

1. 打开"更多"页面
2. 找到"数据同步"卡片
3. 在"GitHub Token"输入框中粘贴你的 Token
4. 点击"保存"

### 第三步：同步数据

#### 导出数据（你对象操作）
1. 记录完数据后，点击"📤 导出到 GitHub"按钮
2. 首次导出会创建一个新的 Gist，请记下 Gist ID
3. 将 Gist ID 分享给你

#### 导入数据（你操作）
1. 在"Gist ID"输入框中输入对方分享的 Gist ID
2. 点击"保存"
3. 点击"📥 从 GitHub 导入"按钮
4. 确认导入后页面会自动刷新，显示最新数据

## 数据同步范围

以下数据会被同步：
- 心情记录 (love_mood_records)
- 饮食记录 (love_diet_records)
- 身体记录 (love_body_records)
- 待办事项 (love_todos)
- 悄悄话 (love_whispers)
- 配置 (love_config)

## 注意事项

1. **Token 安全**：Token 保存在本地 localStorage 中，不会上传到任何服务器
2. **Gist 隐私**：创建的 Gist 是私有的（secret），只有知道 Gist ID 的人才能访问
3. **数据覆盖**：导入操作会覆盖本地所有数据，请谨慎操作
4. **手动同步**：不会自动同步，需要手动点击导出/导入按钮
5. **网络要求**：需要能够访问 GitHub API

## 常见问题

**Q: 导入时提示"Gist 中未找到数据文件"**
A: 请确认 Gist ID 正确，且对方已经成功导出过数据。

**Q: 导出失败提示权限错误**
A: 请检查 Token 是否有 `gist` 权限，或者 Token 是否已过期。

**Q: 如何更换 Token？**
A: 点击 Token 旁边的"修改"按钮，输入新的 Token 后保存。

**Q: 两个人都可以导出吗？**
A: 可以，但建议约定好由谁主要负责导出，避免数据冲突。
