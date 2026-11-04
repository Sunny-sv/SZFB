---
name: dlc-frontend-source
description: >-
  读取或对照数智分拨 DLC 前端工程（DLC Project / cuckoo-vue-dlc）时使用。
  硬约束：只看 uat 分支；对字段/列表/原型时必须按 pm-frontend-code-read 读全列配置，禁止扫片段就落字段。
  改 DLC 原型壳层、查现网布局/交互/文案、对字段与菜单时启用。
  与 TVM / tvm-frontend-source 互不替代，按项目分别启用。
---

# DLC 前端代码来源

## 何时使用

- 要读、搜、对照 **DLC Project** / `cuckoo-vue-dlc` 的前端代码
- 按现网改 **DLC PC 端通用框架**、画 DLC 相关原型、核对页面布局 / 菜单 / 字段 / 交互
- 用户提到 DLC、数智分拨前端、DLC uat 现网代码

**不混用：** 本 skill 只管 DLC；TVM 走 [tvm-frontend-source](../tvm-frontend-source/SKILL.md)。两套母版、两套现网，互不覆盖。

## 分支硬约束

| 项 | 要求 |
|----|------|
| 仓库路径 | `DLC Project/cuckoo-vue-dlc` |
| **唯一可读分支** | **`uat`** |
| 禁止 | 默认用 `master` / `release` / `pre` / `dev` 或其他特性分支当现网依据 |

操作要求：

1. 读代码前先确认当前在 **`uat`**（`git rev-parse --abbrev-ref HEAD` 或等价检查）
2. 若不在 `uat`：先 `checkout uat`（或只读查看 `uat` / `origin/uat`），再继续；不要在别的分支上当现网结论
3. 用户未特别点名其他分支时，**一律只读 uat**
4. **对字段 / 画列表 / 改原型列**：必须同时遵循 [pm-frontend-code-read](../pm-frontend-code-read/SKILL.md)——读全表头/列配置再改，禁止只扫「改名」关键词

## 与原型的关系

| 项 | 路径 / 约定 |
|----|-------------|
| DLC 母版 | `docs/_共用/PC端通用框架.html` |
| 默认主题（uat） | ztpurple：侧栏 `#1c2531`，顶栏 / 选中 `#0658d9`，文案「数智分拨 \| DLC」 |
| 画原型 | 配合 [pc-prototype](../pc-prototype/SKILL.md)，**DLC 需求复制 DLC 母版**，不要用 TVM 母版 |
