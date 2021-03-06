---
layout:     post
title:      个人vscode配置
category: blog
description: 备份自己的vscode设置
---

<h2>备份自己的vscode设置</h2>

<h3>首先是用户代码块:</h3>

HTML:
```
{
"ss": {
	"prefix": "ss",
	"body": [
		"<script src=\"$1\"></script>"
	],
	"description": "<script src=\"...\"></script>"
},
"htm": {
	"prefix": "htm",
	"body": [
		"<!DOCTYPE html>",
		"<html lang=\"zh-CN\">",
		"",
		"<head>",
		"  <meta charset=\"UTF-8\">",
		"  <meta name=\"viewport\" content=\"width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0\">",
		"  <meta http-equiv=\"X-UA-Compatible\" content=\"ie=edge\">",
		"  <title>${1:Document}</title>",
		"</head>",
		"",
		"<body>",
		"  $2",
		"</body>",
		"",
		"</html>"
	],
	"description": "HTML5"
}
}
```

JavaScript:
```
{
	"dg": {
		"prefix": "dg",
		"body": [
			"document.getElementById($1)"
		],
		"description": "document.getElementById(id)"
	},
	"dq": {
		"prefix": "dq",
		"body": [
			"document.querySelector($1)"
		],
		"description": "document.querySelector(querySelector)"
	},
	"fuc": {
		"prefix": "fuc",
		"body": [
			"function $1(){}"
		],
		"description": "function(){}"
	},
	"cl": {
		"prefix": "cl",
		"body": [
			"console.log($1)"
		],
		"description": "Log output to console"
	}
}
```
<h3>然后是设置vscode:</h3>
```
{
  "editor.fontFamily": "Source code Pro,Menlo,Monaco,'Courier New'",
  "editor.renderLineHighlight": "none",
  "editor.lineHeight": 27,
  "extensions.autoUpdate": true,
  "editor.fontSize": 17,
  "editor.tabSize": 2,
  "editor.fontLigatures": true,
  "editor.cursorBlinking": "expand",
  "files.associations": {
    "*.ejs": "html",
    "*.wxml": "html",
    "*.wxss": "css",
    "*.vue-html": "html",
    "*.vue": "html"
  },
  "vetur.format.defaultFormatter.js": "vscode-typescript",
  "javascript.format.insertSpaceBeforeFunctionParenthesis": true,
  "eslint.autoFixOnSave": true,
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "html",
    "vue",
    {
      "language": "html",
      "autoFix": true
    },
    {
      "language": "vue",
      "autoFix": true
    }
  ],
  "eslint.options": {
    "useEslintrc": true,
    "configFile": "C:/Users/wangyu/.eslintrc"
  },
  "emmet.syntaxProfiles": {
    "vue-html": "html",
    "vue": [
      "css",
      "html",
    ]
  },
  "emmet.includeLanguages": {
    "vue-html": "html",
    "vue": "html"
  },
  "workbench.colorTheme": "One Dark Pro",
  "highlightLine.borderColor": "#7f848e",
  "highlightLine.borderStyle": "groove",
  "highlightLine.borderWidth": "1px",
  "editor.wordBasedSuggestions": false,
  "editor.minimap.enabled": false,
  "editor.parameterHints": false,
  "emmet.triggerExpansionOnTab": true,
  "emmet.showExpandedAbbreviation": "never",
  "emmet.showAbbreviationSuggestions": false,
  "editor.tabCompletion": true,
  "editor.acceptSuggestionOnEnter": "off",
  "html.suggest.ionic": false,
  "editor.showFoldingControls": "always",
  "html.suggest.angular1": false,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "window.enableMenuBarMnemonics": false,
  "editor.quickSuggestionsDelay": 370,
  "editor.acceptSuggestionOnCommitCharacter": false,
  "editor.snippetSuggestions": "top",
  "workbench.iconTheme": "vscode-great-icons",
  "explorer.confirmDragAndDrop": false,
  "explorer.confirmDelete": false,
  "fileheader.Author": "wangyu",
  "fileheader.LastModifiedBy": "wangyu",
  "fileheader.tpl": "\r\n// {author} was created in {createTime}\r\n \r\n// @Last Modified by   : {lastModifiedBy}\r\n// @Last Modified time : {updateTime}\r\n \r\n",
  "gitlens.advanced.messages": {
    "suppressShowKeyBindingsNotice": true,
    "suppressUpdateNotice": true,
    "suppressWelcomeNotice": true
  },
  "sync.gist": "1510f745eb912875812e3a9ee09deba6",
  "sync.lastUpload": "2018-08-14T03:28:53.466Z",
  "sync.autoDownload": false,
  "sync.autoUpload": false,
  "sync.lastDownload": "",
  "sync.forceDownload": false,
  "sync.host": "",
  "sync.pathPrefix": "",
  "sync.quietSync": false,
  "sync.askGistName": false,
  "files.autoSave": "afterDelay",
  "git.enableSmartCommit": true,
  "editor.quickSuggestions": {
    "strings": true
  },
  "element-helper.version": "2.2",
  "gitlens.keymap": "alternate",
  "sync.removeExtensions": true,
  "sync.syncExtensions": true,
  "git.confirmSync": false,
  "workbench.startupEditor": "newUntitledFile",
}
```

<h3>快捷键设置：</h3>

```
// 将键绑定放入此文件中以覆盖默认值
[
  {
    "key": "ctrl+j",
    "command": "editor.action.triggerSuggest",
    "when": "editorHasCompletionItemProvider && editorTextFocus && !editorReadonly"
  },
  {
    "key": "ctrl+space",
    "command": "-editor.action.triggerSuggest",
    "when": "editorHasCompletionItemProvider && editorTextFocus && !editorReadonly"
  },
  {
    "key": "ctrl+l",
    "command": "extension.htmlTagWrap",
    "when": "editorTextFocus"
  },
  {
    "key": "alt+w",
    "command": "-extension.htmlTagWrap",
    "when": "editorTextFocus"
  },
  {
    "key": "ctrl+oem_1",
    "command": "editor.action.formatDocument",
    "when": "editorTextFocus && !editorReadonly"
  },
  {
    "key": "shift+alt+f",
    "command": "-editor.action.formatDocument",
    "when": "editorTextFocus && !editorReadonly"
  },
  {
    "key": "ctrl+r",
    "command": "editor.action.startFindReplaceAction"
  },
  {
    "key": "ctrl+h",
    "command": "-editor.action.startFindReplaceAction"
  },
  {
    "key": "ctrl+k",
    "command": "selectNextSuggestion",
    "when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
  },
  {
    "key": "ctrl+down",
    "command": "-selectNextSuggestion",
    "when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
  },
  {
    "key": "ctrl+i",
    "command": "selectPrevSuggestion",
    "when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
  },
  {
    "key": "ctrl+up",
    "command": "-selectPrevSuggestion",
    "when": "editorTextFocus && suggestWidgetMultipleSuggestions && suggestWidgetVisible"
  }
]
```

<h3>插件,使用环境是vue:</h3>

```
  auto-rename-tag v0.0.15
  better-comments v1.2.6
  bracket-pair-colorizer v1.0.59
  code-settings-sync v3.0.0
  color-highlight v2.3.0
  easy-less v1.4.5
  gitignore v0.5.0
  gitlens v8.5.4
  highlight-line-vscode v0.0.1
  html-css-class-completion v1.17.1
  html-snippets v0.2.1
  htmltagwrap v0.0.7
  indenticator v0.6.0
  JavaScriptSnippets v1.7.0
  jquerysnippets v0.0.1
  markdown-preview-enhanced v0.3.5
  Material-theme v2.15.4
  npm-intellisense v1.3.0
  open-html-in-browser v0.1.21
  output-colorizer v0.1.2
  path-autocomplete v1.12.0
  path-intellisense v1.4.2
  stylelint v0.38.1
  vetur v0.12.4
  vscode-auto-open-markdown-preview v0.0.4
  vscode-babel-coloring v0.0.4
  vscode-element-helper v0.5.3
  vscode-eslint v1.4.12
  vscode-fileheader v0.0.2
  vscode-filesize v2.1.1
  vscode-great-icons v2.1.41
  vscode-html-css v0.2.0
  vscode-language-pack-zh-hans v1.26.3
  vscode-markdownlint v0.19.0
  vscode-npm-script v0.3.5
  vscode-regexp-preivew v0.0.3
  vscode-standardjs v1.2.3
  vue-snippets v0.1.8
  vue-vscode-snippets v1.3.0
```

<h3>eslint配置.eslintrc</h3>

```
{
  "plugins": [
    // "react",
    // "html"
  ],
  "env": {
    "node": true,
    "jquery": true,
    "es6": true,
    "browser": true
  },
  "globals": {
    "angular": false,
    "__DEV_MODEL__": true,
    "__DEV__": true,
    "__QA__": true,
    "__YZ__": true,
    "__DEMO__": true,
    "__PROD__": true
  },
  "parser": "babel-eslint",
  "rules": {
    //官方文档 http://eslint.org/docs/rules/
    //参数：0 关闭，1 警告，2 错误
    // "quotes": [0, "single"],                  //建议使用单引号
    "no-inner-declarations": [
      1,
      "both"
    ], //不建议在{}代码块内部声明变量或函数
    "no-extra-boolean-cast": 1, //多余的感叹号转布尔型
    "no-extra-semi": 0, //多余的分号
    "no-extra-parens": 0, //多余的括号
    "no-empty": 1, //空代码块
    //使用前未定义
    "no-use-before-define": [
      0,
      "nofunc"
    ],
    "complexity": [
      0,
      10
    ], //圈复杂度大于*
    //定义数组或对象最后多余的逗号
    "comma-dangle": [
      0,
      "never"
    ],
    // 不允许对全局变量赋值,如 window = 'abc'
    "no-global-assign": [
      "error",
      {
        // 定义例外
        // "exceptions": ["Object"]
      }
    ],
    "no-var": 1, //用let或const替代var
    "no-const-assign": 2, //不允许const重新赋值
    "no-class-assign": 2, //不允许对class重新赋值
    "no-debugger": 1, //debugger 调试代码未删除
    "no-console": 0, //console 未删除
    "no-constant-condition": 2, //常量作为条件
    "no-dupe-args": 2, //参数重复
    "no-dupe-keys": 2, //对象属性重复
    "no-duplicate-case": 2, //case重复
    "no-empty-character-class": 2, //正则无法匹配任何值
    "no-invalid-regexp": 2, //无效的正则
    "no-func-assign": 2, //函数被赋值
    "valid-typeof": 1, //无效的类型判断
    "no-unreachable": 2, //不可能执行到的代码
    "no-unexpected-multiline": 2, //行尾缺少分号可能导致一些意外情况
    "no-sparse-arrays": 1, //数组中多出逗号
    "no-shadow-restricted-names": 2, //关键词与命名冲突
    "no-undef": 1, //变量未定义
    "no-unused-vars": 1, //变量定义后未使用
    "no-cond-assign": 2, //条件语句中禁止赋值操作
    "no-native-reassign": 2, //禁止覆盖原生对象
    "no-mixed-spaces-and-tabs": 0,
    //代码风格优化 --------------------------------------
    "no-irregular-whitespace": 0,
    "no-else-return": 0, //在else代码块中return，else是多余的
    "no-multi-spaces": 0, //不允许多个空格
    //object直接量建议写法 : 后一个空格前面不留空格
    "key-spacing": [
      0,
      {
        "beforeColon": false,
        "afterColon": true
      }
    ],
    "block-scoped-var": 1, //变量应在外部上下文中声明，不应在{}代码块中
    "consistent-return": 1, //函数返回值可能是不同类型
    "accessor-pairs": 1, //object getter/setter方法需要成对出现
    //换行调用对象方法  点操作符应写在行首
    "dot-location": [
      1,
      "property"
    ],
    "no-lone-blocks": 1, //多余的{}嵌套
    "no-labels": 1, //无用的标记
    "no-extend-native": 1, //禁止扩展原生对象
    "no-floating-decimal": 1, //浮点型需要写全 禁止.1 或 2.写法
    "no-loop-func": 1, //禁止在循环体中定义函数
    "no-new-func": 1, //禁止new Function(...) 写法
    "no-self-compare": 1, //不允许与自己比较作为条件
    "no-sequences": 1, //禁止可能导致结果不明确的逗号操作符
    "no-throw-literal": 1, //禁止抛出一个直接量 应是Error对象
    //不允return时有赋值操作
    "no-return-assign": [
      1,
      "always"
    ],
    //不允许重复声明
    "no-redeclare": [
      1,
      {
        "builtinGlobals": true
      }
    ],
    //不执行的表达式
    "no-unused-expressions": [
      0,
      {
        "allowShortCircuit": true,
        "allowTernary": true
      }
    ],
    "no-useless-call": 1, //无意义的函数call或apply
    "no-useless-concat": 1, //无意义的string concat
    "no-void": 1, //禁用void
    "no-with": 1, //禁用with
    "space-infix-ops": 0, //操作符前后空格
    //jsdoc
    "valid-jsdoc": [
      0,
      {
        "requireParamDescription": true,
        "requireReturnDescription": true
      }
    ],
    //标记未写注释
    "no-warning-comments": [
      1,
      {
        "terms": [
          "todo",
          "fixme",
          "any other term"
        ],
        "location": "anywhere"
      }
    ],
    "curly": 1 //if、else、while、for代码块用{}包围
  }
}
```

<h3>最后是Settings Sync:用来同步vscode的设置</h3>

```
Shift + Alt + u 输入在github为vs code创建的Token,上传配置到github里面的gist
Shift + Alt + d 打开输入框,输入 gist id,下载配置及插件到本地
GitHub Token: bf01fff379aaaf746c4a559a8b013004f510b7fd
GitHub Gist: 1510f745eb912875812e3a9ee09deba6
```
