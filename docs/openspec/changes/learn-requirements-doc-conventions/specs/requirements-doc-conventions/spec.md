## ADDED Requirements

### Requirement: Document types SHALL be distinguished by purpose

The repository MUST use distinct document types: full PRD, conclusion summary, and meeting/confirmation record. Each type SHALL follow its designated structure and MUST NOT mix purposes in one file.

#### Scenario: Authoring a new feature PRD

- **WHEN** a feature enters the PRD stage after prototype review
- **THEN** the author creates a full PRD using skeleton A (default) with version history and detailed需求描述 sections

#### Scenario: Capturing discussion outcomes before PRD

- **WHEN** business rules are aligned in discussion but detailed UI is not finalized
- **THEN** the author creates a conclusion summary (需求结论摘要) listing scope, decisions, out-of-scope items, and pending PRD items

#### Scenario: Recording stakeholder meetings

- **WHEN** a requirements walkthrough or confirmation meeting occurs
- **THEN** the author creates a meeting record (需求确认记录 / 对接记录) separate from the PRD body

---

### Requirement: Full PRD SHALL use skeleton A by default

A full PRD MUST include the following top-level sections in order, unless explicitly continuing skeleton B for an existing document series.

| Order | Section | Content |
|-------|---------|---------|
| Header | Title | `# {功能名称}`；大模块可加 `【YYYYMM】数智分拨 - {名称}` 前缀 |
| Header | Stakeholders | 需求涉及部门 / 需求确认人表格 |
| 一 | 概述 | 版本修订表：版本、修订人、修订时间、修订说明、开发负责人、测试负责人 |
| 二 | 要解决的问题 | 按版本列问题陈述 |
| 三 | 业务分析 | 3.1 用户调研（按版本） |
| 四 | 需求分析 | 4.1 需求价值、4.2 用户群体、4.3 优先级及功能点 |
| 五 | 详细需求描述 | 5.1 相关链接、5.2 权限说明、5.3 需求描述 |

#### Scenario: New maintenance-page PRD

- **WHEN** authoring a new WMS maintenance or configuration page PRD
- **THEN** all six section groups above are present with version tables populated for the initial release row

#### Scenario: Continuing an existing 【2508】 series document

- **WHEN** editing a document that already uses skeleton B (文档综述 / 需求分析 / 详细需求描述)
- **THEN** the author MAY keep skeleton B but MUST append a new revision row and version-scoped需求 blocks without restructuring prior content

---

### Requirement: Version entries SHALL be incremental and traceable

Each release MUST use semantic version `V{major}.{minor}.{patch}`. New behavior MUST be described under a version heading (e.g. `### V1.3.0`) in 详细需求描述, and MUST add rows to 概述、要解决的问题、用户调研、需求价值 tables for that version.

#### Scenario: Minor rule change on existing page

- **WHEN** a single field or validation rule changes
- **THEN** the author increments minor or patch version, adds one row per affected summary table, and documents only the delta under the new version heading in section 五

#### Scenario: Reader traces why V8.2.0 exists

- **WHEN** a reader opens the PRD overview tables
- **THEN** they can find the problem statement, research note, and value proposition for V8.2.0 without reading the full detailed section

---

### Requirement: Detailed requirements SHALL describe UI and rules in tabular and numbered form

Section 五 (需求描述) MUST structure each feature area with subsections: 查询条件, 按钮, 弹框, 数据列表 (and 计算规则 when applicable). Field definitions MUST use tables with columns at minimum: 名称/字段, 组件/说明, and 说明/默认值 where relevant.

#### Scenario: Query filter specification

- **WHEN** defining list-page filters
- **THEN** each filter is a table row with component type, enum values, default, and permission-based visibility (总部/省区/分拨)

#### Scenario: CRUD operation specification

- **WHEN** defining 新增/编辑/删除/导入
- **THEN** each operation is documented with 前置条件, step-by-step flow as numbered lists, validation rules, success message, and failure message text

---

### Requirement: Domain vocabulary SHALL follow WMS logistics payroll conventions

Documents MUST use consistent domain terms and enums unless marked 待确认.

| Concept | Standard terms |
|---------|----------------|
| Geography / org | 全国、省区、分拨中心、分拨 |
| Dimension (维度) | 全国、省区、分拨、岗位、人员 — scope of a rule row |
| Effective status | 待生效、生效中/使用中、已失效 |
| Effective period | 有效月份 / 有效期限 — 开始月份、结束月份；开始不得早于当月（维护类） |
| Permission tiers | 总部、省区用户、分拨用户 — data scope MUST be stated |
| Prototype | 墨刀 modao.cc link in 5.1.2 |
| Task tracking | ones 链接 in 5.1.1 |

#### Scenario: Person-dimension maintenance

- **WHEN** a rule applies to specific employees
- **THEN** 维度=人员 is documented with 分拨 + 人员 binding rules, and whether 离职人员 is selectable is explicitly stated

#### Scenario: Edit lock after effective start

- **WHEN** documenting edit behavior for time-bound rules
- **THEN** the PRD states: if 有效开始时间 ≥ 当月 then all fields editable; else only 有效结束时间 editable

---

### Requirement: Import and validation rules SHALL enumerate errors explicitly

Import features MUST document: template columns, required fields, file format (xlsx/xls/csv), size limit, all-or-nothing behavior, and a numbered 异常说明 list mapping condition → exact error message.

#### Scenario: Import failure on duplicate effective period

- **WHEN** import row overlaps existing data in the same dimension scope
- **THEN** the PRD specifies error text such as 「维护时间段内，已有重复数据」 or 「有效时间重复，数据保存失败」 consistent with sibling modules

---

### Requirement: File naming and placement SHALL reflect business domain

PRD files MUST use descriptive Chinese names with optional version prefix. Related documents SHOULD be grouped in domain folders (e.g. `机叉:叉车组长绩效需求/`). Cross-cutting small changes MAY live at repository root.

#### Scenario: Forklift team lead performance iteration

- **WHEN** multiple PRDs belong to one business initiative
- **THEN** they are placed under the same domain folder with a shared conclusion summary linking module-level decisions

---

### Requirement: Writing style SHALL be B端 readable and audit-friendly

Body text MUST be Chinese. Field names and status enums MAY use English abbreviations where industry-standard. The author MUST NOT fabricate customer names, contract data, or undecided business rules — unknowns MUST be labeled 待确认. Narrative MUST avoid C端 marketing tone; focus on roles, processes, exceptions, and acceptance.

#### Scenario: AI-generated PRD draft

- **WHEN** an AI assistant drafts content for this repository
- **THEN** output follows skeleton A, uses tables for fields and operations, and marks unresolved business decisions as 待确认 rather than silent defaults
