# LaTeX All-in-One Template Collection

一个全功能的 LaTeX 模板集合，包含报告模板和演示文稿主题，支持中文排版。

A comprehensive LaTeX template collection featuring report templates and presentation themes with Chinese language support.

## 几种开箱方式
full: texlive-full 版本，功能最全，镜像构建速度慢，占用 5.6GB 磁盘空间。
nano: tectonic only. 镜像构建速度快，第一次编译时需要下载缺失的包，不支持一边保存一边预览，占磁盘空间最小
tiny: tinytex + tectonic. 中等大小，缺失的包需要自己用 tlmgr 安装，只适配了 x86_64 系统

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

In nano env, you can use `tectonic main.tex` to compile.
