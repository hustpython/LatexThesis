# VsCode + textLive 环境配置与说明

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