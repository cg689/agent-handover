# Agent 项目交接全真演练指南（实战速查）

本文档通过 **真实场景对话演练**，直观演示如何在不同 AI 编程助手之间进行无缝项目交接。

---

## 🎯 极简心智模型（3 秒理解）

```
旧 Agent（老师傅） ──[一句话收尾]──► 生成 HANDOVER.md (交接便签)
                                           │
                                           ▼ 同一个项目文件夹
新 Agent（新师傅） ◄──[一句话入职]─── 读便签 + 跑测试 + 验货归档
```

---

## 🎬 演练一：从 Antigravity 切换到 Cursor

### 步骤 1：在 Antigravity 中交出项目
打开 Antigravity 对话框，发送：
> **你**：“帮我做项目交接，我打算换到 Cursor 开发了。”

🤖 **Antigravity 自动执行并回复**：
> “收到。正在为您执行收尾工作：
> 1. ✅ 已检查 Git 状态，所有改动已提交（Commit: `feat: 完成用户模块初始设计`）。
> 2. ✅ 已打防崩回滚点：`git tag handover-before-20260829-1930`。
> 3. ✅ 已生成 `HANDOVER.md`（状态：`PENDING`），记录了技术栈、已知问题与技术债。
> 
> 请在 Cursor 中打开本项目文件夹，并输入：`@agent-handover 我刚从 Antigravity 切换过来，请阅读 HANDOVER.md 完成入职验证。`”

---

### 步骤 2：在 Cursor 中打开项目
1. 打开 Cursor 软件。
2. 点击 **File -> Open Folder**，选择同一个项目文件夹。
3. （可选）将桌面包里的 `adapted/cursor/.cursor/` 目录拷入项目根目录。

---

### 步骤 3：在 Cursor 中接手入职
打开 Cursor Composer 或 Chat，发送第一句话：
> **你**：“@agent-handover 我刚从 Antigravity 切换过来，请阅读 HANDOVER.md 完成入职验证，全程先不要修改代码。”

🤖 **Cursor 自动执行并回复**：
> “您好！我已经阅读了 `HANDOVER.md` 和项目说明书，并已在终端执行了 `npm install` 与 `npm test`：
> - **架构理解**：这是一个基于 React + Node.js 的管理后台。
> - **运行状态**：测试全部通过（4/4 green）。
> - **已知事项**：注意到前任留下的已知问题：登录验证码接口偶尔超时。
> 
> 我已准备就绪，请给我指派一个受控小任务进行动手验证。”

---

### 步骤 4：派发小任务与归档闭环
> **你**：“请修复登录按钮文本的错别字，将‘登入’改成‘登录’。”

🤖 **Cursor 修改完成后**：
1. 生成 `git diff` 给你看。
2. 你确认只改了这一个字，没有误碰其他逻辑。
3. Cursor 自动执行归档：将 `HANDOVER.md` 移动到 `docs/handover/HANDOVER_20260829_Antigravity_to_Cursor.md`。

🎉 **交接圆满结束！正式开始日常开发。**

---

## 🎬 演练二：从 Cursor / Claude Code 切换到 Antigravity

### 步骤 1：在旧工具中收尾
在 Cursor / Claude Code 中发送：
> **你**：“帮我做项目交接，准备换到其他工具开发。”
> *(旧工具自动提交代码、打 Tag、生成 `HANDOVER.md`)*

### 步骤 2：在 Antigravity 中接手
1. 打开 Antigravity，点击 **File -> Open Folder** 选择该项目。
2. 在 Antigravity 对话框直接发第一句话：
> **你**：“我刚从其他 Agent 切换过来，请按流程入职。”

🤖 **Antigravity 会全自动**：
1. 识别根目录处于 `PENDING` 状态的 `HANDOVER.md`。
2. 进入只读模式，自动跑测试并向你做入职汇报。
3. 在你确认小任务合格后，自动完成 `docs/handover/` 归档。

---

## 📋 10 款主流 Agent 触发口令速查卡

| 工具 | 怎么告诉它发起交接（交出） | 怎么告诉它入职接手（接收） |
|---|---|---|
| **Antigravity** | `帮我做项目交接` | `我刚从其他 Agent 切换过来，请按流程入职` |
| **Claude Code** | `/agent-handover 帮我做交接` | `/agent-handover 我刚接手项目，请完成入职验证` |
| **Cursor** | `@agent-handover 帮我做交接` | `@agent-handover 我刚接手项目，请完成入职验证` |
| **ChatGPT Codex** | `帮我做项目交接` | `我刚从其他 Agent 切换过来，请阅读 HANDOVER.md 入职` |
| **Trae** | `帮我做项目交接` | `我刚从其他 Agent 切换过来，请阅读 HANDOVER.md 入职` |
| **Workbuddy** | `帮我做项目交接` | `我刚从其他 Agent 切换过来，请阅读 HANDOVER.md 入职` |
| **DeepSeek Harness**| `帮我做项目交接` | `我刚从其他 Agent 切换过来，请阅读 HANDOVER.md 入职` |
| **Hermes** | `帮我做项目交接` | `我刚从其他 Agent 切换过来，请按技能入职` |
| **豆包Work** | `@agent-handover 帮我做交接` | `@agent-handover 我刚接手，请阅读 HANDOVER.md 入职` |
| **Pi** | 粘贴指令并说 `帮我做交接` | 粘贴指令并说 `我刚接手项目，请完成入职验证` |

---

## 🆘 急救与异常处理锦囊

1. **新 Agent 跑测试挂了怎么办？**
   - 不要慌！看报错是“环境缺依赖/缺密码”还是“代码原本就有 Bug”。
   - 如果缺依赖，让新 Agent 补齐安装命令；如果本来就有 Bug，核对 `HANDOVER.md` 中是否已记录为历史遗留。

2. **新 Agent 搞砸了想一键回滚怎么办？**
   - 在终端里直接敲：
     ```bash
     git checkout handover-before-YYYYMMDD-HHMM
     ```
     项目瞬间回到交接前的最干净状态！

3. **老 Agent 的会话需要关掉吗？**
   - **保留窗口**，作为 1~2 周的“只读技术顾问”。
   - 如果新 Agent 遇到不懂的深坑，可以回老 Agent 窗口问：“*你当初为什么这么设计？*”，但**切记不要再让老 Agent 改文件**。
