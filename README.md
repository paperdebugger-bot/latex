# LaTeX All-in-One Template Collection

一个全功能的 LaTeX 模板集合，包含报告模板和演示文稿主题，支持中文排版。

A comprehensive LaTeX template collection featuring report templates and presentation themes with Chinese language support.

## 📚 目录 | Contents

- [功能特色 | Features](#功能特色--features)
- [项目结构 | Project Structure](#项目结构--project-structure)
- [快速开始 | Quick Start](#快速开始--quick-start)
- [报告模板 | Report Template](#报告模板--report-template)
- [演示文稿主题 | Beamer Theme](#演示文稿主题--beamer-theme)
- [字体配置 | Font Configuration](#字体配置--font-configuration)
- [编译要求 | Compilation Requirements](#编译要求--compilation-requirements)
- [许可证 | License](#许可证--license)

## 🌟 功能特色 | Features

### 中文支持 | Chinese Support
- ✅ 完整的中文字体支持 (Full Chinese font support)
- ✅ 自动字体回退机制 (Automatic font fallback)
- ✅ XeLaTeX 编译优化 (XeLaTeX compilation optimized)

### 报告模板 | Report Template
- ✅ 现代化页面布局 (Modern page layout)
- ✅ 自定义颜色方案 (Custom color schemes)
- ✅ 智能图片插入 (Smart image insertion)
- ✅ 信息框和警告框 (Info and warning boxes)
- ✅ 自定义页眉页脚 (Custom headers and footers)

### 演示文稿主题 | Presentation Theme
- ✅ Arguelles 主题 (Elegant Arguelles theme)
- ✅ 多种字体权重 (Multiple font weights)
- ✅ 灵活的导航选项 (Flexible navigation options)
- ✅ 背景图片支持 (Background image support)

## 📁 项目结构 | Project Structure

```
latex/
├── README.md                    # 本文档 | This documentation
├── LICENSE                      # MIT 许可证 | MIT License
├── report/                      # 报告模板 | Report template
│   ├── main.tex                # 主文档示例 | Main document example
│   ├── reportstyle.sty         # 自定义样式包 | Custom style package
│   └── Makefile                # 编译脚本 | Build script
└── beamer/                     # Beamer 演示主题 | Beamer presentation theme
    ├── main.tex                # 演示示例 | Presentation example
    ├── README.md               # Arguelles 主题文档 | Arguelles theme docs
    ├── beamerthemeArguelles.sty # 主题主文件 | Main theme file
    ├── beamercolortheme*.sty   # 颜色主题 | Color theme
    ├── beamerfonttheme*.sty    # 字体主题 | Font theme
    ├── beamerinnertheme*.sty   # 内部主题 | Inner theme
    ├── beameroutertheme*.sty   # 外部主题 | Outer theme
    └── assets/                 # 资源文件 | Asset files
```

## 🚀 快速开始 | Quick Start

### 克隆仓库 | Clone Repository

```bash
# 递归克隆所有子模块 | Clone with all submodules
git clone --recursive <repo-url>

# 或者后续初始化子模块 | Or initialize submodules later
git clone <repo-url>
cd latex
git submodule update --init --recursive
```

### 系统要求 | System Requirements

- **TeX 发行版 | TeX Distribution**: TeX Live 2020+ 或 MiKTeX
- **编译引擎 | Compilation Engine**: XeLaTeX (推荐 | Recommended)
- **Make 工具 | Make Tool**: GNU Make (可选 | Optional)

## 📄 报告模板 | Report Template

### 快速使用 | Quick Usage

```bash
cd report/
make                    # 编译文档 | Compile document
make view              # 打开 PDF | Open PDF
make clean             # 清理临时文件 | Clean temp files
```

### 手动编译 | Manual Compilation

```bash
xelatex main.tex
xelatex main.tex        # 两次编译确保交叉引用 | Compile twice for cross-references
```

### 自定义样式 | Style Customization

`reportstyle.sty` 提供了丰富的自定义功能：

**颜色定义 | Color Definitions**
```latex
\definecolor{primarycolor}{RGB}{0,128,128}   % 主色调 | Primary color
\definecolor{secondarycolor}{RGB}{70,130,180} % 辅助色 | Secondary color
\definecolor{accentcolor}{RGB}{255,165,0}    % 强调色 | Accent color
```

**自定义命令 | Custom Commands**
```latex
\highlight{高亮文本}      % 高亮背景 | Highlighted background
\emphtext{强调文本}       % 彩色粗体 | Colored bold text
\code{代码文本}          % 等宽字体 | Monospace font
```

**信息框 | Information Boxes**
```latex
\begin{infobox}
    信息内容 | Information content
\end{infobox}

\begin{warningbox}
    警告内容 | Warning content
\end{warningbox}

\begin{successbox}
    成功信息 | Success message
\end{successbox}
```

**智能图片插入 | Smart Image Insertion**
```latex
\smartimage[0.8\textwidth]{image.png}{占位符标题}{占位符描述}
% 如果图片存在则显示图片，否则显示占位符
% Shows image if exists, otherwise shows placeholder
```

## 🎨 演示文稿主题 | Beamer Theme

### Arguelles 主题 | Arguelles Theme

基于著名的 Arguelles beamer 主题，具有优雅简洁的设计。

Based on the renowned Arguelles beamer theme with elegant and clean design.

### 使用方法 | Usage

```latex
\documentclass[aspectratio=169]{beamer}
\usetheme{Arguelles}

% 可选参数 | Optional parameters
% \usetheme[sans]{Arguelles}      % 无衬线字体 | Sans-serif fonts
% \usetheme[frameno]{Arguelles}   % 显示帧号 | Show frame numbers
% \usetheme[splitnav]{Arguelles}  % 分割导航 | Split navigation
```

### 主题特性 | Theme Features

- **字体系统 | Font System**: Alegreya 字体家族，支持多种字重
- **颜色方案 | Color Scheme**: 基于 Open Color 库的现代配色
- **布局选项 | Layout Options**: 多种导航和编号选项
- **背景支持 | Background Support**: 支持背景图片和渐变

### 示例代码 | Example Code

```latex
\begin{frame}
    \frametitle{标题 | Title}
    \framesubtitle{副标题 | Subtitle}
    
    内容示例 | Content example
    \begin{itemize}
        \item 列表项 1 | Item 1
        \item 列表项 2 | Item 2
    \end{itemize}
\end{frame}

% 背景图片帧 | Background image frame
\begin{frame}[bg=assets/background.png]
    \frametitle{带背景的幻灯片 | Slide with Background}
\end{frame}

% 突出显示帧 | Standout frame
\begin{frame}[standout]
    \centering
    重要信息 | Important Message
\end{frame}
```

## 🔤 字体配置 | Font Configuration

### 中文字体优先级 | Chinese Font Priority

1. **Noto 字体系列 | Noto Font Family** (推荐 | Recommended)
   - Noto Serif CJK SC
   - Noto Sans CJK SC
   - Noto Sans Mono CJK SC

2. **Fandol 字体系列 | Fandol Font Family** (备选 | Fallback)
   - FandolSong
   - FandolHei
   - FandolFang

3. **系统默认 | System Default** (最后备选 | Last resort)
   - SimSun
   - SimHei

### 西文字体 | Western Fonts

- **主字体 | Main Font**: Noto Serif / DejaVu Serif
- **无衬线 | Sans-serif**: Noto Sans / DejaVu Sans  
- **等宽字体 | Monospace**: Noto Sans Mono / DejaVu Sans Mono

## ⚙️ 编译要求 | Compilation Requirements

### 必需软件包 | Required Packages

**报告模板 | Report Template**:
- `xeCJK`, `fontspec` (中文支持 | Chinese support)
- `amsmath`, `amsfonts`, `amssymb` (数学公式 | Math formulas)
- `graphicx`, `booktabs`, `float` (图表支持 | Figure/table support)
- `fancyhdr`, `geometry`, `xcolor` (页面布局 | Page layout)
- `mdframed`, `lastpage` (高级功能 | Advanced features)

**Beamer 主题 | Beamer Theme**:
- `alegreya`, `eulervm`, `mathalpha` (字体 | Fonts)
- `microtype`, `fontawesome5` (排版优化 | Typography)
- `opencolor`, `enumitem`, `parskip` (样式 | Styling)
- `pgf`, `tcolorbox` (图形 | Graphics)

### 编译命令 | Compilation Commands

```bash
# 报告模板 | Report template
xelatex main.tex

# Beamer 演示 | Beamer presentation  
xelatex main.tex
# 或 | or
pdflatex main.tex  # 如果不需要特殊字体 | If no special fonts needed
```

## 🛠️ 故障排除 | Troubleshooting

### 常见问题 | Common Issues

1. **字体缺失 | Missing Fonts**
   ```bash
   # 安装 Noto 字体 | Install Noto fonts
   sudo apt install fonts-noto-cjk fonts-noto
   ```

2. **编译错误 | Compilation Errors**
   - 确保使用 XeLaTeX 编译 | Ensure using XeLaTeX
   - 检查软件包是否完整安装 | Check if packages are properly installed

3. **中文显示问题 | Chinese Display Issues**
   - 验证字体是否正确安装 | Verify fonts are correctly installed
   - 检查编码设置 | Check encoding settings

## 📜 许可证 | License

- **报告模板 | Report Template**: MIT License
- **Arguelles 主题 | Arguelles Theme**: MIT License (原作者: Michele Piazzai)

## 🤝 贡献 | Contributing

欢迎提交 Issue 和 Pull Request！
Welcome to submit Issues and Pull Requests!

## 📞 联系 | Contact

如有问题，请提交 Issue 或联系维护者。
For questions, please submit an Issue or contact the maintainer.
