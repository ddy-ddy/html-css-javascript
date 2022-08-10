## 基础语法

#### 1. 注释

```javascript
//This is an in-line comment

/* This is a 
multi-line comment */
```

#### 2. 声明变量

- JavaScript 8种数据类型：`undefined`, `null`, `boolean`, `string`, `symbol`, `bigint`, `number`, and `object`.
- Variables允许计算机以动态方式存储和操作数据，上述数据类型均可存储在variable中.
- 使用关键字`var`声明一个变量.

```javascript
var myName;
```

#### 3. 给变量赋值

```javascript
//	先声明变量，再赋值
var a;// 声明变量
var a=7;// 给变量赋值
// 一行代码实现初始化+赋值
var a=9;
```

#### 4. 声明字符串变量

```javascript
var myFirstName="Duan";
var myLastName="Yu";
```

#### 5. 字符串相加

```javascript
// Only change code below this line
var a=5;
var b=10;
var c="I am a";
// Only change code above this line
a = a + 1;
b = b + 5;
c = c + " String!";
```

#### 8. 变量命名

- 大小写敏感
- 将大写变量标识符用于不可变值，将小写或驼峰形式用于可变值（对象和数组）。
- 示例命名: `var someVariable`, `var anotherVariableName`, `var thisVariableNameIsSoLong`

```javascript
// Variable declarations
var studlyCapVar;
var properCamelCase;
var titleCaseOver;

// Variable assignments
studlyCapVar = 10;
properCamelCase = "A String";
titleCaseOver = 9000;
```

#### 9. var, let和const的区别

- 使用`let`时，同名的变量只能声明一次
- `const`声明的变量是只读的
- [the difference of var, let and const](https://www.geeksforgeeks.org/difference-between-var-let-and-const-keywords-in-javascript/#:~:text=The%20scope%20of%20a%20let%20variable%20is%20block%20scope.,re%2Ddeclared%20into%20the%20scope.)

```javascript
// let
let catName = "Oliver";
let catSound = "Meow!";

// const
const FCC = "freeCodeCamp"; // Change this line
let fact = "is cool!"; // Change this line
fact = "is awesome!";
console.log(FCC, fact); // Change this line
```

#### 10. 计算

```javascript
// 加法
const sum = 10 + 0;
// 减法
const difference = 45 - 0;
// 乘法
const product = 8 * 0;
// 除法
const quotient = 66 / 33;
// 自加
let myVar = 87;
myVar++;
// 自减
let myVar = 11;
myVar--;
// 求余
const divider= 13 % 3;
// 复合运算
let a = 3;
a += 12;
a -= 6;
a *= 5;
a /= 12;
```

