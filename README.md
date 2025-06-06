# XMU-Template-EN

厦门大学本科英文毕业论文 LaTeX 模版。

该模版基于 [F5Soft 的厦门大学本科毕业论文 LaTeX 模板](https://github.com/F5Soft/xmu-template) 制作而成，结合 [Atrovast 的修改](https://github.com/Atrovast/xmu-template)，对照《厦门大学本科毕业论文（设计）规范》与外文学院本科毕业论文调整英文格式。

毕业论文模版除了主修毕业论文外，还支持辅修版本和毕业设计版本。详细使用示例可查看 example.tex 文件。

## Features

- 自动生成封面、诚信承诺书、中英目录
- 支持将封面改为“本科毕业设计”
- 支持在封面中添加“（辅修）”
- 中英文摘要、中英文目录支持
- 章节自动编号
- 根据章节自动进行插图、表格、公式、算法编号
- 自动设置奇数、偶数页眉和页脚
- 支持从 bib 文件导入参考文献，将自动按照 GB/T 7714-2005 设置参考文献的引用格式
- 支持附录、附表，以及在附录中添加附录章节
- 同时支持电子版和打印版，如果设成打印版，将会在某些偶数页产生空白，使得下一部分的内容从奇数页开始
- 致谢环境可以自定义放在摘要前或论文最后
- 自带字体文件，兼容缺少 Windows 版宋体和黑体字体的 Linux 和 macOS 系统
- 严格按照《厦门大学本科毕业论文（设计）规范》设置字体、行距等

## 改动

- 在封面上显示“主修专业”或“辅修专业”（原模板不显示主修专业）
- 若无校外指导教师，自动移除封面中“校内指导教师”的“校内”两字。
- 调节封面信息字体大小为小三号，日期字体大小为四号
- 修改封面间距以默认适应 2 行标题
- 修改诚信承诺书标题为加粗的宋体
- 增加诚信承诺书页码
- 移动致谢至最前并从中英文目录中移除（原模板在最后）
- 前置页是否需要插入空白与具体页码计算方式不明。当前版本将插入空白页，但不计算前置部分空白页的页码（正文中空白页仍将计算）。可在明确要求后进入 "xmu.cls" 文件中修改调试 `\prepagecleardouble` 有关部分，也可导出 PDF 文件后手动编辑前置页面。
- 将致谢、参考文献、附录章节标题改为英文“Acknowledgements”、“References”、“Appendix”。若有需要（如撰写中文摘要）可进入 "xmu.cls" 文件相应部分自行修改。
- 各级标题在目录仍为双语，但在论文内容中将只显示英文
- 论文内容中一、二、三级英文标题统一使用加粗的 Times New Roman，四级英文标题为不加粗的 Times New Roman
- 将编号中中文的“图”、“表”、“算法”改为英文的“Figure”、“Table”、“Algorithm”
- 默认始终在章节标题前显示“Chapter”。若不需要，可进入模板“titleformat”处自行修改。
- 恢复 LaTeX 默认数学公式字体
- 加入数学定理证明环境，默认提供 Theorem 与 Lemma。其中证明将显示为“Proof”而非“证明”。
- 修改所有页眉为英文
- 改正参考文献目录页码
- 改用 biblatex 实现引用（仍符合 GB/T 7714-2005 标准）。默认采用著者出版年制，若需要使用顺序编码制可进入 "xmu.cls" 文件将`\RequirePackage[backend=biber,citestyle=gb7714-2005ay,bibstyle=gb7714-2005ay,isbn=false,doi=false,url=false]{biblatex}` 一行中 "citestyle" 与 "bibstyle" 修改为 "gb7714-2005"
- 默认从参考文献中删除ISBN、DOI、URL

## 毕业论文模版示例

见 example.tex 文件。可以直接在该示例基础上修改。

编译时，需要确保 example.tex 文件和 xmu.cls 文件在同一目录内，并使用 xelatex 进行编译。如果使用 pdflatex 编译则可能编译失败。

> 如果编译失败（尤其是 macOS系统），请**使用 xelatex 进行编译**。如果使用的是 VSCode 的 Latex Workshop 插件，需要选择 Recipe: latexmk (xelatex) 这一项。

论文中的所有插图需统一放在 figures 文件夹内，并根据文件名来包含。

如果您没有接触过 LaTeX 环境，可以尝试安装 Tex Live 和 VSCode 中的 LaTeX Workshop 插件，通过 VSCode 打开 example.tex 文件，并参考网上的 LaTeX 教程以尝试使用本模版。

## 自定义模版

xmu.cls 和 xmu-slide.cls 文件分别是毕业论文模版文件和毕业答辩幻灯片模版文件，可以自己修改这两个模版文件。模版文件中也提供了大量注释便于修改。

如果您认为自己修改的效果不错，可以发起 Pull request 贡献代码。也可以发起 Issue 提出要添加的功能。
