---
layout:     post
title:      个人vscode配置
category: blog
description: 备份自己的vscode设置
---

备份自己的vscode设置

HTML:
```
{
/*
	// Place your snippets for HTML here. Each snippet is defined under a snippet name and has a prefix, body and 
	// description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
	// same ids are connected.
	// Example:
	"Print to console": {
		"prefix": "log",
		"body": [
			"console.log('$1');",
			"$2"
		],
		"description": "Log output to console"
	}
*/
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
	/*
	// Place your snippets for JavaScript here. Each snippet is defined under a snippet name and has a prefix, body and 
	// description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
	// same ids are connected.
	// Example:
	"Print to console": {
		"prefix": "log",
		"body": [
			"console.log('$1');",
			"$2"
		],
		"description": "Log output to console"
	}
*/
	"dg": {
		"prefix": "dg",
		"body": [
			"document.getElementById($1)"
		],
		"description": "document.getElementById(id)"
	},
	"fuc": {
		"prefix": "fuc",
		"body": [
			"function(){$1}"
		],
		"description": "function(){}"
	},
	"cl": {
		"prefix": "cl",
		"body": [
			"console.log($1);"
		],
		"description": "Log output to console"
	}
}
```
vscode:
```
{
  "editor.fontFamily": "Source code Pro,Menlo,Monaco,'Courier New'",
  "editor.renderLineHighlight": "none",
  "editor.lineHeight": 27,
  "editor.roundedSelection": false,
  "extensions.autoUpdate": true,
  "editor.fontSize": 16,
  "editor.tabSize": 2,
  "files.associations": {
    "*.ejs": "html",
    "*.wxml": "html",
    "*.wxss": "css",
    "*.vue-html": "html",
    "*.vue": "html"
  },
  "vetur.format.defaultFormatter.js": "vscode-typescript",
  "javascript.format.insertSpaceBeforeFunctionParenthesis": true,
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "vue"
  ],
  "eslint.options": {
    "useEslintrc": true,
    "configFile": "C:/Users/wangyu/Desktop/app/.eslintrc"
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
    "javascript": "javascriptreact",
    "vue": "html"
  },
  "editor.quickSuggestions": {
    "other": true,
    "strings": true
  },
  "workbench.colorTheme": "One Dark Pro",
  "editor.wordBasedSuggestions": false,
  "editor.minimap.enabled": false,
  "editor.parameterHints": false,
  "emmet.triggerExpansionOnTab": true,
  "emmet.showExpandedAbbreviation": "never",
  "emmet.showAbbreviationSuggestions": false,
  "editor.tabCompletion": true,
  "editor.acceptSuggestionOnEnter": "off",
  "workbench.sideBar.location": "right",
  "html.suggest.ionic": false,
  "editor.showFoldingControls": "always",
  "html.suggest.angular1": false,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "window.menuBarVisibility": "toggle",
  "window.enableMenuBarMnemonics": false,
  "editor.quickSuggestionsDelay": 350,
  "editor.acceptSuggestionOnCommitCharacter": false,
  "editor.snippetSuggestions": "top",
  "workbench.iconTheme": "vscode-great-icons",
  "explorer.confirmDragAndDrop": false,
  "explorer.confirmDelete": false,
  "fileheader.Author": "wangyu",
  "fileheader.LastModifiedBy": "wangyu",
  "fileheader.tpl": "\r\n// {author} was created in {createTime}\r\n \r\n// @Last Modified by   : {lastModifiedBy}\r\n// @Last Modified time : {updateTime}\r\n \r\n",
  "gitlens.advanced.messages": {
    "suppressCommitHasNoPreviousCommitWarning": false,
    "suppressCommitNotFoundWarning": false,
    "suppressFileNotUnderSourceControlWarning": false,
    "suppressGitVersionWarning": false,
    "suppressLineUncommittedWarning": false,
    "suppressNoRepositoryWarning": false,
    "suppressUpdateNotice": false,
    "suppressWelcomeNotice": true
  },
  "sync.gist": "de21ca67b784e7f3281c808997046e8a",
  "sync.lastUpload": "2017-12-15T15:39:13.150Z",
  "sync.autoDownload": false,
  "sync.autoUpload": false,
  "sync.lastDownload": "",
  "sync.forceDownload": false,
  "sync.anonymousGist": false,
  "sync.host": "",
  "sync.pathPrefix": "",
  "sync.quietSync": false,
  "sync.askGistName": false
}
```
快捷键设置：
```
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
  }
]
```
插件:
```
auto-rename-tag v0.0.15
  bracket-pair-colorizer v0.10.14
  code-settings-sync v2.8.7
  easy-less v1.4.5
  gitlens v7.0.0
  html-css-class-completion v1.14.0
  htmltagwrap v0.0.6
  JavaScriptSnippets v1.5.0
  jquerysnippets v0.0.1
  Material-theme v2.11.0
  open-html-in-browser v0.1.21
  output-colorizer v0.1.2
  path-autocomplete v1.7.0
  path-intellisense v1.4.2
  stylelint v0.31.0
  vetur v0.11.5
  vscode-babel-coloring v0.0.4
  vscode-codemetrics v1.11.2
  vscode-css-peek v2.0.2
  vscode-eslint v1.4.3
  vscode-fileheader v0.0.2
  vscode-filesize v1.0.0
  vscode-great-icons v2.1.22
  vscode-markdownlint v0.12.0
  vscode-regexp-preivew v0.0.3
  vscode-standardjs v1.2.0
  vue-peek v1.0.2
  vue-snippets v0.1.5
  vue-vscode-snippets v1.2.0
```
eslint配置.eslintrc
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
Settings Sync:
用来同步vscode的设置,懒人神器
Shift + Alt + u 输入在github为vs code创建的Token,上传配置到github里面的gist
Shift + Alt + d 打开输入框,输入 gist id,下载配置及插件到本地
GitHub Token: 0b8b87dc01687cd9eeebc3026819a609c51510ff
GitHub Gist: 3c9349cc5e94dbb32902964a42a37f8a
