# Math-Note-Template-By-Yukina

一个面向数学笔记与书籍写作的 LaTeX 模板，基于 `ctexbook` 构建，内置统一的定理环境体系、数学符号库与交换图支持。

## 目录结构

```
.
├── main.tex              # 主文件：定义 \part 并汇总各章节
├── structure.sty         # 核心样式：页面布局、定理环境、符号库、引用
├── quiver.sty            # 交换图支持（q.uiver.app 导出，封装 tikz-cd）
├── commit.sh             # 一键提交脚本（可选）
├── Content/              # 正文内容，按部分（part）分目录管理
│   └── 01_Test_title_one/
│       ├── index.tex     # 章节汇总，\input 本部分各节
│       ├── 01_test_title_1.tex
│       ├── 02_test_title_2.tex
│       └── 03_test_title_3.tex
└── Figures/              # 插图目录
```

## 模板特点

### 1. 中文书籍排版

使用 `ctexbook`（10pt / A4 / oneside），几何边距左右 1.5cm、上下 2cm，适合中文数学书籍与长篇笔记。

### 2. 统一的定理环境体系

基于 `tcolorbox` 预置 20 种环境，按类别配色、共用章节编号、可跨页断行：

| 类别 | 环境 |
|------|------|
| 基础陈述 | 定义（蓝）、公理（靛蓝）、假设（青） |
| 推演结论 | 定理（红）、引理（橙）、命题（紫）、推论（绿）、元定理（靛蓝）、准则（茶） |
| 补充说明 | 问题（黄）、例（绿）、注记（灰） |
| 其他 | 算法、约定、警示、证明（自动加 ∎）、回答、分析、提示、代码块 |

每个环境带独立学术配色与顶边色条，视觉统一且易于区分。

### 3. 智能引用

`hyperref` + `cleveref`：`\cref` / `\autoref` 自动带类型名（显示"定义 1.1"而非"1.1"），中英文引用名均已配置。

### 4. 交换图支持

`quiver.sty` 封装 `tikz-cd`，可直接使用 q.uiver.app 导出的交换图，支持弯曲箭头、路径缩短与多种箭头样式。

### 5. 预置数学符号库

内置代数 / 几何 / 分析三大类常用记号，如 `\N \Z \Q \R \C`、`\Hom \End \Aut`、`\coker \coim \tor`、`\GL \SL \SO`、`\closure \interior` 等，面向抽象代数、范畴论与线性代数写作。

### 6. 内容分层管理

`main.tex` → `\part` → `Content/<部分>/index.tex` → `\input` 各节，将长文档拆分为小文件，便于维护与复用。

## 更新日志

详细更新记录见 [ChangeLog.md](./ChangeLog.md)。

## 使用

用 XeLaTeX 编译 `main.tex` 即可。新增章节时，在 `Content/` 下新建目录与 `index.tex`，再于 `main.tex` 中以 `\input` 引入。
