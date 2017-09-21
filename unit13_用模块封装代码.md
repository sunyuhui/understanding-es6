### 什么是模块

模块是自动运行在 **严格模式** 下并且 **没有办法退出运行** 的 Javascript 代码

在模块的顶部，`this` 指向的是 `undefined`。

模块真正的魔力所在是仅导出和导入你需要的绑定，而不是将所用东西都放到一个文件。

在模块内部，不能使用 `if` 条件判断等方式来动态导入、导出，比如：

```javascript
if(flag){
	export name;
	import {sum} from './example.js'
}
```

可以动态改变变量来避免这个问题

### 导出的基本语法

export

### 导入的基本语法

`import {identifier1, identifier2} from "./example.js"`

`{identifier1, identifier2}` 表示一个导入的绑定,看起来与 **解构** 相似，但不是解构

从其他模块中导入一个绑定，就好像使用 `const` 定义一样，不能定义同名变量，不能改变绑定值

为了更好的兼容多个浏览器和 Node.js 环境，一定要在字符串之前包含 **/、 ./、 ../** 来表示要导入的文件。

#### 导入单个绑定

`import {sum} from './example.js'`

#### 导入多个绑定

`import {sum, sub} from './example.js'`

#### 导入整个模块

`import * as example from './example.js'`

使用 sum: `example.sum()`

### 导出和导入时的重命名

使用 `as` 即可重命名

```javascript
export {sum as add}
import {add as newName} from './example.js'
```
### 模块的默认值

```javascript
import sum from './example.js'
``` 
与导入给默认值的区别是：没有使用大括号，sum 是一个本地名称，不一定是`example.js`中的变量名，sum 用来表示模块默认导出的任何变量

使用 **默认值** 进行导入导出是最纯净的，这也是使用 es6 的模块语法时的最佳实践

#### 同时使用默认值与非默认值

```javascript
//导出
export let color='red'
export default function(num1, num2) {
	return num1 + num2
}
//导入
import sum, {color} from './example.js'
```
使用逗号区分，同时默认值需要在非默认值之前




