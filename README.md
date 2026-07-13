# SZFB 产品原型库

转运可视化平台等产品需求的 HTML 线框原型，供产品评审、开发对齐、测试参考使用。

> **在线预览入口**：https://sunny-sv.github.io/SZFB/  
> 下方表格中的「预览链接」可直接点开查看页面效果（非源码）。

---

## 原型索引

| 原型名称 | 预览链接 | 文件名 | 说明 |
|---|---|---|---|
| PC 端通用框架 | [打开预览](https://sunny-sv.github.io/SZFB/pc-admin-framework.html) | `pc-admin-framework.html` | 企业后台母版，新页面原型可基于此扩展 |
| 合托达成率（电商拆分） | [打开预览](https://sunny-sv.github.io/SZFB/he-tuo-da-cheng-lv-ecommerce.html) | `he-tuo-da-cheng-lv-ecommerce.html` | 合托达成率按电商/非电商拆分展示 |
| 基础提成方案维护 | [打开预览](https://sunny-sv.github.io/SZFB/jicha-forklift-performance-scheme.html) | `jicha-forklift-performance-scheme.html` | 机叉叉车组长绩效方案维护 |
| 机叉叉车组长绩效标准报表 | [打开预览](https://sunny-sv.github.io/SZFB/jicha-forklift-performance-standard-report.html) | `jicha-forklift-performance-standard-report.html` | 保底绩效、质量绩效等标准展示 |
| 货量重量配置（组合区间） | [打开预览](https://sunny-sv.github.io/SZFB/cargo-weight-config-interval.html) | `cargo-weight-config-interval.html` | 调整比例，组合区间配置 |
| 区间维度配置 | [打开预览](https://sunny-sv.github.io/SZFB/interval-dimension-config.html) | `interval-dimension-config.html` | 区间维度动态交互配置 |

---

## 如何查看

### 方式一：在线预览（推荐）

1. 点击上表「预览链接」列
2. 或访问首页：https://sunny-sv.github.io/SZFB/pc-admin-framework.html

> 若链接暂时打不开，请到仓库 **Settings → Pages** 确认已开启 Pages，并等待 1～3 分钟生效。

### 方式二：本地打开

```bash
git clone https://github.com/Sunny-sv/SZFB.git
cd SZFB
open pc-admin-framework.html   # macOS
```

用浏览器直接打开任意 `.html` 文件即可。

---

## 使用说明

- 本仓库仅为**交互原型**，不含后端逻辑，数据为页面内模拟
- 原型确认后，以 PRD 文档为准；原型与 PRD 冲突时以 PRD 为准
- 新增或更新原型后，提交到 `main` 分支，Pages 会自动同步（通常 1～3 分钟）

---

## Pages 管理地址

仓库所有者可在以下位置查看/配置在线预览：

**Settings → Pages → Your site is live at**

https://github.com/Sunny-sv/SZFB/settings/pages
