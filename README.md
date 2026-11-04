# SZFB 产品文档与原型

转运可视化平台等 B 端需求的 **PRD + HTML 线框原型**，按项目放在同一目录，便于评审与对齐。

远程仓库：https://gitee.com/hu_mian_fei/szfb

---

## 目录结构

```
docs/
  _共用/                 # PC 端母版（画新原型从此复制）
  {项目名}/
    *.md                 # PRD / 对接纪要
    *.html               # 同项目原型（中文文件名）
.cursor/
  skills/                # 产品协作 skills
  rules/                 # Cursor 规则
```

| 项目 | 路径 |
|------|------|
| 母版 | [`docs/_共用/PC端通用框架.html`](docs/_共用/PC端通用框架.html) |
| 合托 | [`docs/合托/`](docs/合托/) |
| 外包工相关 | [`docs/外包工相关/`](docs/外包工相关/) |
| 百分比重量 | [`docs/百分比重量/`](docs/百分比重量/) |
| 薪资线上化 | [`docs/薪资线上化/`](docs/薪资线上化/) |
| 分批配载 | [`docs/分批配载/`](docs/分批配载/) |
| 微信公众号奖罚查询 | [`docs/微信公众号奖罚查询/`](docs/微信公众号奖罚查询/) |
| 转运人员排班维护 | [`docs/转运人员排班维护/`](docs/转运人员排班维护/) |

---

## 在线预览（Gitee Pages）

入口：https://hu_mian_fei.gitee.io/szfb/

仓库根目录的 `index.html` 列出全部原型；也可直接打开例如：

https://hu_mian_fei.gitee.io/szfb/docs/合托/合托达成率-电商拆分.html

> 仓库网页里点开 `.html` **不能**交互预览，必须走上面的 Pages 链接。  
> 若打不开：仓库 → **服务** → **Gitee Pages** → 部署分支选 `main`、目录选 `/`（根目录）→ 启动 / 更新；公开仓库才可免费预览。每次有新提交后，若页面未变，到 Pages 页再点一次「更新」。

## 本地查看

用浏览器直接打开 `docs/{项目名}/` 下对应 `.html` 即可。

新增 PC 原型：复制 `docs/_共用/PC端通用框架.html` → 放到对应项目目录 → 使用中文文件名 → 同步在根目录 `index.html` 加一条预览链接。

---

## 说明

- 原型为交互线框，数据为页面内模拟
- 原型确认后以 PRD 为准；冲突时以 PRD 为准
- 源文件按项目在 `docs/`；在线预览靠根目录 Pages + `index.html` 索引
