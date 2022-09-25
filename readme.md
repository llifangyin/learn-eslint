# 守住优雅的护城河
+ 参考链接 ![eslint](https://zhuanlan.zhihu.com/p/184951182 '知乎无名之辈')

> ESlint: Find and fix problems in your Javascript code
 ![eslint官网](https://eslint.org/ '知乎无名之辈')

## lint工具进化史 
1. 2008年JSLint 对于糟粕的语法是严格不让使用
2. 2011年JSHint 
+ 更多可配置的规则
+ 代码模块化
+ 命令行工具的支持，很好得和各种 IDE 集成
3. 2013年ESLint 
+ 将源代码解析成 AST,然后检测 AST 来判断代码是否符合规则
+ ES6发布JSHint短期无法支持，Babel为ESLint提供了解析器支持。

## 如何使用

1. npm init
2. npm init @babel/config
选择配置项：
```js
module.exports = {
  env: {
    browser: true,
    es2021: true
  },
  extends: [
    'plugin:vue/vue3-essential',
    'standard'
  ],
  overrides: [
  ],
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module'
  },
  plugins: [
    'vue'
  ],
  rules: {
  }
}

```
3. 使用 npx eslint yourfile.js
## 常用配置规则
两种配置方式
1、在文件里注释
2、配置文件
配置内容：
+ Env
+ Globals
+ extends
+ Plugins
+ Rules

## 环境与全局变量 Env && Globals
 + 构建时提供选择
 Javascript modules(import/export)
 CommonJS(require/exports)
 None of these
 + framework
 react vue.js none of these 
+ typescript? 
+ where code run ?
browser node
+ config file format
#### 配置全局变量
配置文件中配置运行环境或者框架提供的全局变量
```js
{
    "globals": {
        "$": "readonly"
    }
}
```
+ 或者预设env
```js
 env: {
    jquery: true
  }
```
## 扩展 rules extends
rules 用来配置 ESLint 的规则
ESLint 使用 extends 配置来一次性生效一整套规则
+ ESLint支持三种类型的扩展：
1. 'eslint:' 开头的 ESLint 官方扩展。包括 eslint:recommended 和 eslint:all
2. 共享的扩展。通过 npm 包提供一套共享的配置，包名前缀必须为 eslint-config-
3. 插件中提供的扩展 eslint-config-standard 的依赖,会被自动安装
## 插件 Plugins
初始化项目内置好了
```js
 plugins: [
    'vue'
  ],
```

## VSCode自带插件
ESLint一堆设置
## git插件 约束代码提交信息规范、提交代码校验规则
+  commitizen、cz-conventional-changelog、standard-version、commintLint

