# 像塑特效制作 Skill

一个可复用的 Codex Skill，帮助你在像塑中制作、预览、修改和保存人像特效。内容来自一次完整的边框特效制作与回退过程，重点是把设计意图落到实际预览，并处理导入贴图缓存造成的“文件已改、画面没变”。

## 包含内容

- `SKILL.md`：Skill 入口与核心制作流程。
- `references/production-workflow.md`：项目检查、素材来源、资源导入、预览迭代和交付清单。

仓库只包含可复用的流程说明，不包含特效工程、人物预览图或第三方素材。

## 安装

将 `xiangsu-effect-creation` 文件夹放入 Codex 的 skills 目录（例如 `~/.codex/skills/`），然后在像塑特效相关任务中使用 `$xiangsu-effect-creation`。

也可以下载 ZIP 并解压后安装。Skill 需要在本机可用像塑编辑环境中操作项目；它本身不替代像塑，也不包含一键生成特效的模板。
