
0.0.1：2/24，探索基本功能的实现，遇到很多项目启动的难点。
0.0.2：2/25，实现 Mend 的核心功能。对实现有进一步的认识。
0.0.3：2/26，编写文档并成功部署。

todo:
异常处理与 mend 反馈。
选择性返回、拦截。mock or axios。

废弃设想：
校验（可能会重新启用）。参考如下。Mock.valid ( template, data )。校验真实数据 `data` 是否与数据模板 `template` 匹配。


# Mendjs 的核心实现

``` js
Promise封装为Mend

1.增加mend-cover、mend-message
mend-feedback对象。包括mend-cover、mend-message
Promise对象.then(res => Object.assign(res,...mend-feedback));

2.挂载方法
a=Promise对象
a.with
a.
```





4. 测试export和export default是否可以共存。可以。
5. 测试发现export dafault后面不能加const。
6. 测试export default是否可以直接加函数、箭头函数。可以。
7. 发现export default后容易犯的错误。import是命名导入而不是解构赋值。

8.全局安装nodemon并启动。npm nodemon -g。nodemon。





