# Latex 创建华中科技大学硕士毕业论文

## 环境配置

软件:texlive 2018 + vscode 

1，vscode的颜色主题对代码高亮的支持的影响。


2，文档和代码之间跳转功能的支持，需要编译过程中的临时文件的支持。

    "latex-workshop.latex.clean.enabled":flase
    

3，latex preview 代码跳转快捷:ctrl + 双击。

4，由于使用了参考文献，使用混合编译方式。具体设置如下:
   
   ```css

  
    "latex-workshop.latex.tools": [
      {
          "name": "latexmk",
          "command": "latexmk",
          "args": [
              "-synctex=1",
              "-interaction=nonstopmode",
              "-file-line-error",
              "-pdf",
              "%DOC%"
          ]
      },
      {
          "name": "xelatex",
          "command": "xelatex",
          "args": [
              "-synctex=1",
              "-interaction=nonstopmode",
              "-file-line-error",
              "%DOC%"
          ]
      },
      {
          "name": "bibtex",
          "command": "bibtex",
          "args": [
              "%DOCFILE%"
          ]
      },
      {
        "name": "xelatex",
        "command": "xelatex",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
        ]
    },
    {
        "name": "xelatex",
        "command": "xelatex",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
        ]
    }
  ],
  "latex-workshop.latex.recipes": [
      {
          "name": "xelatex -> bibtex -> xelatex*2",
          "tools": [
              "xelatex",
              "bibtex",
              "xelatex",
              "xelatex"
          ]
      }
  ],
   ```

## 模板使用说明



### 封面：

- [中文封面 data\cover.tex](data/cover.tex)

- [英文封面 data\encover.tex](data/encover.tex)

- [声明 data\statement.tex](data/statement.tex)

### 摘要:

- [中文摘要 data\cnabstract.tex](data/cnabstract.tex)


- [英文摘要 data\enabstract.tex](data/enabstract.tex)

### 目录

### 章节

- [第一章 data\chapter1.tex](data/chapter1.tex)

- [第二章 data\chapter2.tex](data/chapter2.tex)

- [第三张 data\chapter3.tex](data/chapter3.tex)

- [第四章 data\chapter4.tex](data/chapter4.tex)

- [第五章 data\chapter5.tex](data/chapter5.tex)

### 致谢

- [致谢 data\acknowledgement.tex](data/acknowledgement.tex)

### 参考文献 

- [参考文献tex data\refs.tex](data/refs.tex)

- [参考文献bib data\refs.bib](data/refs.bib)

### 代码附录 

- [代码 data\appendixcode.tex](data\appendixcode.tex)