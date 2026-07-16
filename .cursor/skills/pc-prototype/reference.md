# PC 端原型 — 布局对照与占位规则

母版文件：`docs/_共用/PC端通用框架.html`  
业务原型：`docs/{项目名}/{中文页面名}.html`（与同项目 PRD 同目录）

## 全局三区 DOM 对照

| 区域 | CSS 类 / 元素 | 说明 |
|------|---------------|------|
| 整体容器 | `.layout` | flex 横排，100vh |
| 左侧侧边栏 | `#sidebar.sidebar` | 宽 200px，折叠 64px |
| Logo 区 | `.sidebar-logo` | 系统名称占位 |
| 菜单列表 | `.sidebar-menu` | `.menu-item` + 可选 `.menu-sub` |
| 折叠按钮 | `#sidebarToggle` | 底部固定 |
| 右侧容器 | `.main-wrapper` | flex 纵排 |
| 顶部标签栏 | `.top-tabs` | 高 40px |
| 页面标签 | `#pageTabs .page-tab` | 可多个，一项 `.active` |
| 主内容滚动区 | `.content-area` |  padding 16px，背景 `#f0f2f5` |
| 内容卡片 | `.content-card` | 白底，承载四模块 |

## 主内容四模块 DOM 对照

| 模块 | CSS 类 / 元素 | 关键结构 |
|------|---------------|----------|
| 1 筛选条件 | `.filter-area` | `.filter-grid`（3 列）+ 右侧 `.filter-actions`；`align-items: flex-end` 与末行底对齐 |
| 1a 单项结构 | `.filter-item` | **左** `.filter-label` + **右** `.filter-control-wrap`（左右布局，勿上下叠） |
| 1b 下拉 | `.select-wrap` + `select.filter-control` | 放在 `.filter-control-wrap` 内 |
| 1c 输入 | `input.filter-control` | 放在 `.filter-control-wrap` 内 |
| 1d 日期 | `.date-range` | 开始 ~ 结束，两个 input，放在 `.filter-control-wrap` 内 |
| 1e 按钮 | `.filter-actions` | `.btn` 重置 + `.btn-primary` 查询 |
| 2 标签切换 | `#contentTabs.content-tabs` | `.content-tab`，一项 `.active` |
| 3 操作按钮 | `.action-bar` | `.btn-action` / `.btn-action.primary` |
| 4 数据表格 | `.table-area` + `.data-table` | thead + tbody；`th`/`td` 默认 `text-align: center` |
| 4a 复选框列 | `.col-checkbox` | 表头 `#checkAll` + 行 `.row-check` |
| 4b 分页 | `.pagination` | 总数 + 页码 + 跳转 |

## 筛选区多行扩展示例

多个筛选条件时，**全部放入同一个 `.filter-grid`（3 列自动换行）**，重置/查询放在右侧独立 `.filter-actions`，按钮与最后一行底对齐：

```html
<section class="filter-area">
  <div class="filter-grid">
    <div class="filter-item">
      <span class="filter-label">筛选条件</span>
      <div class="filter-control-wrap">
        <div class="select-wrap">
          <select class="filter-control"><option>下拉框</option></select>
        </div>
      </div>
    </div>
    <!-- 更多条件… -->
  </div>
  <div class="filter-actions">
    <button class="btn">重置</button>
    <button class="btn btn-primary">查询</button>
  </div>
</section>
```

勿使用「4 列 grid 把按钮塞进第 4 列」，否则第 4 个条件会错位到按钮上方。
勿把筛选名称放在控件上方（上下布局）；统一左右布局。

## 占位命名规范

| 位置 | 未确认时 | 已对齐时 |
|------|----------|----------|
| 侧边菜单 | 菜单项 N / 子菜单 N | 真实菜单路径名 |
| 顶栏标签 | 标签页 N | 真实页面名（如「发运清单查询」） |
| 筛选 label | `.filter-label` 文案「筛选条件」 | 字段中文名（如「运单号」） |
| 筛选控件 | 下拉框 / 输入框 / 开始日期~结束日期 | 按控件类型保留，换 placeholder |
| 内容 Tab | 标签 N | 真实 Tab 名（如「全部单据汇总」） |
| 操作按钮 | 操作按钮 N | 新增 / 导出 / 导入 等 |
| 表格列 | 列 N | 真实列名 |
| 表格单元格 | — | 示例值或 — |
| 分页总数 | 共 N 条 | 可保留占位 |

## 控件类型映射

| 用户描述 | HTML 实现 |
|----------|-----------|
| 下拉 / 枚举 | `select.filter-control` + `.select-wrap` |
| 文本输入 | `input.filter-control[type=text]` |
| 日期 / 日期范围 | `.date-range` 内两个 input |
| 单选 / 多选下拉 | 线框阶段仍用 select，标注「待确认多选」 |
| 主按钮 | `.btn-primary` 或 `.btn-action.primary` |
| 次按钮 | `.btn` 或 `.btn-action` |

## 最小 JS（保留自母版）

| 功能 | 选择器 | 行为 |
|------|--------|------|
| 侧边栏折叠 | `#sidebarToggle` | toggle `#sidebar.collapsed` |
| 顶栏标签切换 | `#pageTabs` | 切换 `.page-tab.active` |
| 内容 Tab 切换 | `#contentTabs` | 切换 `.content-tab.active` |
| 全选 | `#checkAll` | 联动 `.row-check` |

新页面复制母版时 **保留这段 script**，除非用户明确不要交互。

## 与 PRD skill 的字段对应

原型模块 → PRD（pc-maintain-prd）章节：

| 原型模块 | PRD 章节 |
|----------|----------|
| 筛选条件区 | 查询条件 |
| 操作按钮区 | 按钮操作 |
| 数据列表区 | 数据列表 |
| 标签切换区 | 5.3.x 各 Tab/模块 |

原型确认后再写 PRD；PRD 中的字段名应与原型一致。
