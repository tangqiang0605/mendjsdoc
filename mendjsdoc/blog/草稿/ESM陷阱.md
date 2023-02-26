
本文的 esm 指 ES module。
export 导出的在一个对象里面，需要解构使用。export default 导出的，可以直接用一个变量接受。二者还可以并存。import axios from "./axios. js"; import { age } from "./axios. js"; 或者 import axios,{a} from "./axios. js";

导入 import * as axios from "./axios. js"; 不建议对二者进行混用。如果只有 default 但仍用 import * as axios from "./axios. js"; 进行导入。使用时应该用 axios. default。



在export 后面可以加 const，而 export default 后面不行。export const age = 12;

<!-- export default const myname = "zhangsan"错误，要分开写。什么原因不知道。 -->



在import 后面并不是解构赋值，而是命名导出。命名导出会寻找 export 中相同的名字。

错误用法：

```text
# lib.js
export default { 
 a: 1,
 b: 2
}
# main.js
import { a,b } from './lib';
lib中并没有export const a或者export const b，所以ab应该为空。
console.log('a:',a);
console.log('b:',b);
```

正确用法

1. 全部使用 export，然后命名导出即 import {a,b}
2. 全部使用 export，然后 import * as lib。然后呢？再在下面解构赋值吗？
3. 错误用法来分开写，export default。import 用一个变量接受，然后再在下面解构赋值。
