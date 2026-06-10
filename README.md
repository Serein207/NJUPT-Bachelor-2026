## 南京邮电大学本科毕业设计（论文）LaTeX模板（2026届适配）

本项目基于[musnows/NJUPT-Bachelor](https://github.com/musnows/NJUPT-Bachelor)继续维护，并对照南京邮电大学 2026 届毕业设计（论文）理工艺教类 Word 模板做了增量适配。上游模板本身源自[dhiyu/NJUPT-Bachelor](https://github.com/dhiyu/NJUPT-Bachelor)，并合并了若干历史模板的格式修正；本 Fork 主要聚焦 2026 届封面、摘要、目录、关键词等格式差异。

### 介绍

本模板是《南京邮电大学本科生（理工艺教类）毕业设计（论文）》的 LaTeX 模板，该模板由[NJUPThesis-Bachelor](https://github.com/imguozr/NJUPThesis-Bachelor)以及[lemoxiao](https://github.com/lemoxiao)修改过的[NJUPThesis-Bachelor](https://github.com/lemoxiao/NJUPThesis-Scholar)演化而来，并在上游 `musnows/NJUPT-Bachelor` 的基础上继续做 2026 届格式适配。

上游维护者在原作者[dhiyu](https://github.com/dhiyu/NJUPT-Bachelor)的基础上针对2025年本科毕设论文模板的要求做了对应的修正；当前 Fork 在此基础上继续补充 2026 届模板要求中涉及的封面下划线样式、楷体、摘要/目录页码、关键词接排等调整。

* 2021年doc模板文件：[2021 word template](./2021-word-template.rar)
* 2025年doc模板文件：[2025 word template](./2025-word-template.zip)

### 核心特征

- 使用了GBT-7714标准引用格式。上游模板对教务处给出的 Word 版本模板进行研究后，认为其参考文献格式与 GBT-7714 高度一致，因此在模板中使用 GBT-7714 引用格式。
- 修正了封面不在中间的问题
- 修改了页面参数，包括页边距、行距、段间距，页眉、页尾等等，和官方Word保持一致。
- 修改了结束语、致谢、参考文献的标题格式，修改了附录的格式。
- 修复了图注和表标题后面没有空格的问题。
- 修复了公式编号问题。
- 修改了原创性声明的格式，与官方保持一致。
- 其它大量的细节优化和 模板文件(`.cls`)注释添加
- 修改了目录样式，但是请注意没有为四级标题添加匹配（也不符合南邮规范）

### 论文编写指南（必看）

使用本模板编写论文的时候，只需要修改`main.tex`和`reference.bib`两个文件，并将需要插入的图片放入`pic`文件夹中即可。针对这三个需要修改的地方做如下说明：

- `main.tex`: 这是tex源文件，论文全文都是修改这个文件。本仓库已填充了标题、图片、参考文献、附录的示例，可以对照生成的 `main.pdf` 熟悉代码。
- `reference.bib`: 论文的参考文献库。在论文网站复制引用的时候选择bibtex格式，写入reference.bib文件后，正文中使用`\cite{论文}`进行引用，编译时会自动更新参考文献。
- `./pic`: 将图片放入该文件夹，图片支持常规的格式如`eps`, `jpg`, `png` , `pdf`。`pdf`文件可以编译得更快（至少3倍的速度提升），可以通过WPS或者[docsmall](https://docsmall.com/image-to-pdf)批量将图片转为PDF格式。在`main.tex`中只需要`{文件名}`就可以展示图片（不需要图片文件后缀），具体可以参考`main.tex`中已有的图片引用代码。

其余文件**不要修改**，除非你知道它们的作用。

### 使用方式（必看）

若你对 LaTeX 不熟悉，可以使用 [Overleaf](https://cn.overleaf.com/) 或 [TexPage](https://www.texpage.com/) 等在线编辑器。下载本仓库 zip 后通过“上传项目”的方式创建在线项目，在线使用时请以本仓库代码为准。

**温馨提醒**：数据无价，使用在线网站编辑毕设时，请定期下载论文 PDF 和 TeX 源码到本地备份。

如果更在乎数据安全和稳定性，建议在**本地**编辑和编译，避免无网络、网站故障情况下无法编辑论文。

1. 对于 `Windows` 系统，直接安装 `TeX Live` ，编辑器推荐使用`TeXstudio`。
2. `MacOS` 可通过 `brew install mactex` 安装 MacTeX 环境（需要先安装 Homebrew）。
3. [Leo Y Chen](https://github.com/xsro)提供了`vscode`的latex编译配置文件，存放在`.vscode/`文件夹中。vscode 需要安装 [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) 插件。安装完毕此插件后，修改`main.tex`并保存，就会自动触发编译流程，更新`main.pdf`。

### 编译过程

带参考文献的中文文档，一般进行以下四次编译：

`XeLaTeX` -> `BibTeX` -> `XeLaTeX` -> `XeLaTeX`

常用编辑器如 `TeXstudio` 可以在选项->设置->构建中自行配置编译链。如果使用 vscode，本模板已经做好了 LaTeX Workshop 插件的编译流程配置，参考上文。

### 字数统计

字数统计可以通过多种方式进行，摘自：[NJUPThesis-Bachelor](https://github.com/imguozr/NJUPThesis-Bachelor)

1. 在命令行中使用 `texcount your-tex-file-name.tex` 命令进行统计。
2. 对生成的 PDF 文件进行统计。
3. 在vscode中[LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)插件的`侧边栏-杂项-统计LaTeX文档中的词数`，点击后会在右下角弹窗显示当前文档的词数。

### 已知问题

1. ~~早期模板在一些标题和题注格式上为了贴近官方 Word 模板加入了额外空格或间隔，可能影响正文引用效果~~。目前此问题已由[Leo Y Chen](https://github.com/xsro)解决。暂时无问题，欢迎反馈。
2. everypage的功能已经被官方支持所以不再需要这个包，所以这个包会警告，参见[ref](https://stackoverflow.com/questions/64921954/how-to-solve-latex-package-warning-for-everypage)。

#### Fork后的修改点

上游 `musnows/NJUPT-Bachelor` 相对更早模板的修改点（按提交顺序）：

- 摘要名称修改：中文摘要改为`摘要`，英文摘要改成`ABSTRACT`；
- 新增附录自动ABCD编号：附录可以通过多个`\thesisappendix`自动插入附录A、附录B，修复大纲中附录A中字母A字号较小的问题；
- 新增listings来引入代码块，但是不推荐使用（不确定学校是否允许这种格式）；
- 行距1.25倍：latex中的`\linespread{1.35}`才和docx中的1.25倍行距相似（原本是`\linespread{1.25}`，间隙会变小），**论文封面信息部分依旧保持1.25行距**；
- 封面间距缩小：封面南邮标题和论文信息之间的空隙减小，论文制作时间和论文信息之间的空隙减小；
- 参考文献间距修改：参考文献标题和列表之间新增10pt的空隙（原本无空隙）；
- 2025新模板要求英文摘要中Key和words中间有一个空格（原本是Keywords）；
- 2025新模板要求图表序号与图表描述之间只包含一个全角空格（原始模板是两个）；
- gbt7714-numerical.bst格式文件中`show.doi`改为0，参考文献中不显示doi编号（学校要求中不需要doi编号，必须去除）；
- 标题间距修改：原始模板中，中文摘要、英文摘要、结束语、致谢与正文部分间隔1cm，过长，目前间距修正为0.6cm；
- 新增`\createdate`作为原创性声明日期，一般情况下原创性声明日期和论文封面结束日期一致；
- 新增作者签名`\authorsign`和导师签名`\advisorsign`，分别嵌入至原创性声明和论文封面，**注意签名的图片文件上下不要留空白**，否则会影响嵌入签名效果；

#### Serein207 Fork后的修改点

本 Fork 在上游 `musnows/NJUPT-Bachelor` 的基础上继续维护。本节只记录相对上游 `origin/master` 的实际增量差异：

- 字体加载方式改为使用仓库 `Font/` 目录中的 Times、宋体、黑体、楷体字体文件，减少不同系统字体名称不一致带来的编译差异；
- 图表标题由悬挂格式改为居中普通格式，标题宽度调整为 `\textwidth`；
- `subsubsection` 标题字号由小四号调整为四号黑体，与 Word 模板中小节标题要求保持一致；
- 中文摘要标题、结束语、致谢和附录标题显式使用黑体，附录标题改为顶格显示；
- 封面信息表改为按信息栏居中排版，题目、专业、学生姓名、班级学号、指导教师、指导单位统一使用封面单元格格式；封面字段名使用“指导教师”；
- 摘要和目录环境在多页情况下保持无页眉页脚样式，正文从第一章开始恢复页眉页脚和阿拉伯页码；
- 中文关键词和英文 Key words 去掉额外的段前空白，按模板说明与摘要正文接排；关键词标签使用固定宽度，续行与关键词正文起点对齐，英文关键词避免专有名词被连字符拆分。

### Q&A

模板仍可能存在不足，如有问题欢迎提出 issue，也欢迎解决后提交 pull request。

如果觉得好用，可以在致谢部分留下**本论文采用基于 LaTeX 的南京邮电大学本科论文模版编写**，并附上本 GitHub repo 的链接。

### 贡献者名单

- [dhiyu](https://github.com/dhiyu) (Owner)
- [Leo Y Chen](https://github.com/xsro) (Contributer)
- [musnows](https://github.com/musnows/) (Contributer)

### 参考项目

- [imguozr/NJUPThesis-Bachelor](https://github.com/imguozr/NJUPThesis-Bachelor)
- [lemoxiao/NJUPThesis-Bachelor](https://github.com/lemoxiao/NJUPThesis-Scholar)
