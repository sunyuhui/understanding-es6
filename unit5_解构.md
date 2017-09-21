### 为何使用解构功能？

在ES5中从 **数组** 和 **对象** 中获取特定数据并赋值，这个操作非常麻烦

**解构** 的作用就是：简化获取信息的过程

### 对象解构

#### 应用到 **变量声明** 中

```javascript
let node = {
	name: "sunyuhui",
	type: "fe"
}

let {name, type} = node;  //变量声明
console.log(name, type);
```

#### 应用到 **变量赋值** 中

```javascript
let node = {
	type: "fe",
	name: "sunyuhui"
};
let type = "developer";
let name = "sunhui";
({name, type} = node);  //赋值，使用括号扩起来
```

#### 默认值

```javascript
let node = {
	type: "fe",
	name: "sunyuhui"
};
let { type, name, value = true } = node;
```

#### 解构时为变量重新取名

```javascript
let node = {
	type: "fe",
	name: "sunyuhui"
};
let {type: localType, name: localName} = node; //将解构到的 type、name 重新取名
```

#### 嵌套对象解构

知道有这回事

### 数组解构

#### 应用到 变量声明 中

```javascript
let arr = [1,2,3];
let [first, second] = arr;//first: 1, second: 2
```

数组解构按照位置选取值

```javascript
let arr = [1,2,3];
let [, , second] = arr;//second: 3
```

#### 应用到 变量赋值 中

```javascript
let arr = [1,2,3];
let first , second;
[first, second] = arr; //first: 1, second: 2；不需要使用括号括起来
```

#### 交换两个变量的值

```javascript
let a = 1, b = 2;
[a, b] = [b, a];
```
其实就是将数组解构应用到 变量赋值 中去

#### 默认值

```javascript
let arr  = [1, 2, 3];
let [first, second = 4] = arr; //second 使用了默认值
```

#### 嵌套数组解构

知道有这回事



 