
可能将会使用但是未使用的技术：
- yarn 创建 monorepo。
- npm 的 workspace。

## node 支持esm
项目在前期中使用 esm 的模块导入，node 默认不支持 esm，需要对 package. json 进行配置。
`npm init -y`
在 package.json 新增 `"type": "module",` 字段。

## nodemon 监听代码
自动监听并执行 index.js 文件
``npm i nodemon -g
`nodemon`

## ts 类型支持
1. 安装依赖
`npm i typescript -g`
``tsc --init
配置文件
Module”es 6
Strict“false
ModuleResolution：’node
2. 监视 ts 文件
	vscode 终端/运行任务/typescript/监视
	新建 index.ts 文件
3. 关闭尖括号自动补全
	vscode 拓展 auto close tag，配置文件注释掉 md、ts、js。

## mock
[Mock.js (mockjs.com)](http://mockjs.com/examples.html)
`npm i mock -D`
使用方法：
mock 只有两个函数。
``` ts
import mock from 'mock. Js'
mock.Random.csentence()
mock.Mock('@csentence()')
```
Radom 方法和 Mock 方法类似。Mock 还可以生成对象。

## lodash
[Lodash 中文文档 (lodashjs.com)](https://www.lodashjs.com/docs/lodash.assign)
``npm i lodash
by 迭代函数 iteratee 改变值
with 比较器 comparator 比较值


## jest
``npm i jest -D
新建测试文件名：被测试的文件名. test. js
导入要被测试的方法。
``` js
test("介绍",()=>{
    expect(执行导入函数结果).toBe(预期严格内容结果)
    expect(执行导入函数结果).not.toEqual(预期内容结果)
})
```

## vscode 配置
更改快捷方式。保存全部由 ctrl+K+S 转为 ctrl+s，保存从 ctrl+s 转为 ctrl+s o。
关闭尖括号自动补全
	vscode 拓展 auto close tag，配置文件注释掉 md、ts、js。
启动 tsc 监听任务。
上传到 github。