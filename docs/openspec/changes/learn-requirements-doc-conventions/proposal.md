## Why

本仓库是数智分拨（WMS 薪资/绩效域）的需求文档库，现有 PRD 由多人、多时期沉淀，结构相近但章节编号、表格字段、版本写法存在两套习惯。OpenSpec 的 `config.yaml` 尚未写入项目上下文，AI 协作时无法稳定复用既有规范。需要将仓库内可观察到的文档惯例提炼为可执行的规范，供后续写 PRD、改 PRD 时对齐。

## What Changes

- 新增「需求文档规范」能力说明：文档类型、章节骨架、版本管理、表格与交互描述范式
- 将提炼出的领域上下文与写作约束写入 `openspec/config.yaml`，作为 AI 生成 artifact 的默认约束
- 不修改现有业务 PRD 正文（只读归纳，不做批量改写）
- 不引入新的技术实现或代码模块

## Capabilities

### New Capabilities

- `requirements-doc-conventions`: 本仓库 PRD 的结构、命名、版本、表格、交互/异常描述、权限与维度等业务写作规范

### Modified Capabilities

（无。`openspec/specs/` 下尚无既有 spec。）

## Impact

- **文档**：新增 OpenSpec change 产物；可选后续在仓库根目录增加 `README` 或规范索引（本 change 以 config + spec 为主）
- **协作**：Cursor / OpenSpec 生成 proposal、design、tasks 及新 PRD 草稿时，将继承 `openspec/config.yaml` 中的项目上下文
- **业务 PRD**：无直接影响，现有 `.md` 文件保持不变
