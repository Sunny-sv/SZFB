## 1. OpenSpec 配置落地

- [ ] 1.1 将 `specs/requirements-doc-conventions/spec.md` 中的骨架 A、文档类型、领域词汇、写作风格提炼为 `openspec/config.yaml` 的 `context` 字段
- [ ] 1.2 在 `config.yaml` 增加 `rules.proposal` / `rules.design` 约束：中文 B 端语气、不写技术实现、未决标待确认
- [ ] 1.3 运行 `openspec validate --change learn-requirements-doc-conventions` 确认 change 合法

## 2. 规范归档

- [ ] 2.1 将 delta spec 同步至 `openspec/specs/requirements-doc-conventions/spec.md`（apply 或 sync 流程）
- [ ] 2.2 确认归档后 AI 新建 change / artifact 时能读到项目上下文

## 3. 可选增强（需产品确认后执行）

- [ ] 3.1 在仓库根目录增加简短 `README.md`，说明文档类型分工与默认骨架 A（仅当产品同意新增索引文件）
- [ ] 3.2 提供一份空白 PRD 模板 `.md` 供复制起稿（仅当产品同意新增模板文件）

## 4. 验收

- [ ] 4.1 用规范试写一段「查询条件 + 导入异常」样例，对照 `转运人员排班维护.md` 检查格式一致性
- [ ] 4.2 确认未改动任何现有业务 PRD 正文
