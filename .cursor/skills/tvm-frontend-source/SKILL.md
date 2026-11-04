---
name: tvm-frontend-source
description: >-
  凡是要读、搜、打开、对照 TVM Project / ztky-tvm-vue 前端代码时必须使用。
  硬约束：只看 uat 分支；对字段/列表/原型时必须按 pm-frontend-code-read 读全列配置，禁止扫片段就落字段。
  改 TVM 原型壳层、查布局/交互/文案/字段/菜单、对现网实现时启用。
  与 DLC / dlc-frontend-source 互不替代，按项目分别启用。
---

# TVM 前端代码来源

## 何时使用

**只要涉及读 TVM 前端代码，就必须启用本 skill**（不限是否在画原型）：

- 打开 / 搜索 / 对照 **TVM Project** / `ztky-tvm-vue` 任意源码
- 按现网改 **TVM PC 端通用框架**、画 TVM 相关原型、核对页面布局 / 菜单 / 字段 / 交互
- 用户提到 TVM、转运可视化、ztky-tvm-vue、TVM 现网代码

**不混用：** 本 skill 只管 TVM；DLC / 数智分拨走 [dlc-frontend-source](../dlc-frontend-source/SKILL.md)。两套母版、两套现网，互不覆盖。

## 分支硬约束（必守）

| 项 | 要求 |
|----|------|
| 仓库路径 | `TVM Project/ztky-tvm-vue` |
| **唯一可读分支** | **`uat`** |
| 禁止 | 用 `master` / `release` / `pre` / `dev` 或其他特性分支当现网依据 |

操作要求：

1. **读任何 TVM 代码前**先确认当前在 **`uat`**（`git rev-parse --abbrev-ref HEAD` 或等价检查）
2. 若不在 `uat`：先 `checkout uat`（或只读查看 `uat` / `origin/uat`），再继续；不要在别的分支上当现网结论
3. 用户未特别点名其他分支时，**一律只读 uat**
4. 与「只要读 uat」同类约定：DLC 见 [dlc-frontend-source](../dlc-frontend-source/SKILL.md)，两边规则一致、项目分开
5. **对字段 / 画列表 / 改原型列**：必须同时遵循 [pm-frontend-code-read](../pm-frontend-code-read/SKILL.md)——读全表头/列配置再改，禁止只扫「改名」关键词

## 与原型的关系

| 项 | 路径 / 约定 |
|----|-------------|
| TVM 母版 | `docs/_共用/PC端通用框架-TVM.html` |
| 默认主题（uat） | `purple`：侧栏 `#011040`，顶栏 / 主色 `#9174EA`，标题「TVM」 |
| 画原型 | 配合 [pc-prototype](../pc-prototype/SKILL.md)，**TVM 需求复制 TVM 母版**，不要用 DLC 母版 |
