# js 笔记

## js 的组成

- 1.ECMAScript javascript 的语法组合而成.
- 2.DOM 文档对象模型.
- 3.BOM 浏览器对象模型.

## js 的特点

- 1. 简单易用 使用工具种类多 只要浏览器执行程序即可.
- 2. 解释性语言 不需要事先编译 可以直接边解释边执行.
- 3. 基于对象 内置大量对象 只需要少量代码即可实现效果.
- 4. 面向过程.

## js 语言分类

- 解释型语言 边解释边执行 javaScript php.
- 编译型语言 先编译 编译通过后才能执行 java c++,

## js 的引入方式

- 1. 外部引入 注意引入的位置.使用<script scr="xx.js"></script>引入放在</body>前即可
- 2. 内部书写 也要注意书写的位置.<script>在这里面写 js 代码</script>可以在 head 里写 也可以在 body 里写 要主要运行顺序 在 head 里写 要在出口处加上 window.onload.但是在 body 前写就不需要.

## 变量的命名规则

- 1. 变量名是由字母 数字 下划线 和 \$美元符号组合而成 不能是保留字或者是关键字.
- 2. 变量名必须是 字母 下划线 和美元符号组合而成 不能是数字开头 不能用关键字.
- 3. 变量名严格区分大小写.
- 4. 如果是一个单词使用小写 两个或者以上的单词 每个单词的首字母大写 (驼峰式写法).
- 5. 起名字的时候尽量 见字如意.

## 变量的数据类型

- 一是基本数据类型
  - String 字符串:是使用单引号或者双引号引起来的内容.
  - Number 数值 :整数或者浮点数(小数).
    - NAN 表示一个非数 如果是非数 就返回 NAN.
    - isNAN 判断一个数值是不是 NAN 不是就返回 flase 是的话就返 true.
  - Boolean 布尔值：true 和 false 通常用来逻辑判断.
  - Null 空值 ：用来表示一个空的对象 var a = null .
  - Undefined 未定义的值 :声明了一个变量却没有赋值 var b .
- 一是引用数据类型
  - object 对象:属性(键值对)的无序集合,描述事物信息特征
    - var obj = {
      属性名字 : 属性值 ,
      属性名字 1 : 属性值 1 ,
      属性名字 2 : 属性值 2
      }
  - array 数组:Array 数组 有序 数组是一组按顺序排列数据的集合，集合的每个值称为元素,逗号隔开 数组可以包括任意数据类型。但是通常用来表示某一类数据的集合。
    - var arr = [12,36,8,5];
  - function 函数:函数的作用就是封装代码.
    - function 变量名字 (形参){
      代码
      }

## js 的执行顺序

- 由上而下 但是推荐 所有的 js 代码都写在 body 最下面 因为 js 存在的原因就是交互 当所有的页面还没有加载出来 就不可能会有交互效果 而且还可能会报错。 当然也可以写在 head 上面但是 代码出口前面要加上 Window.onload 等待页面加载完成后再 执行 js.

## js 的弹出框

- 1.alert("页面上弹出警告框");
- 2.console.log("控制到上输出信息 。 大部分都是在此处调试程序 程序要必用“);
- 3.prompt("用户输出语句 ");
- 4.document.write("在页面上输出信息 基本上弃用");

## js 数值类型的转换

### 其它类型转为字符串 类型(有三种方式)

1. 方式一 : 调用 toString()方法...

- 数字类型
  var num = 123; num = num.toString();console.log(num);// 123
  var num2 = 345; console.log(num2.toString(2)); //(括号里面的 2 是转换为 2 进制)101011001 2.
- 布尔值 console.log(true.toString()); // true ]
- null 和 undefined 没有 toString 方法
- console.log(null.toString())//会报错的

2. 方式二 使用 String()

- 数字 console.log(String(345)); // 345
- 布尔值 console.log(String(false)); //false
- null 和 undefined console.log(String(undefined)); // undefined
  console.log(String(null)); // null

3. 方式三 +''; 拼接作用 会把内容转换成字符串

- console.log(123); console.log(123 + ''); // 123
- console.log(true + ''); console.log(undefined +''); console.log(null + '');

### 其他类型转换成 Number 使用 Number() 方式

1. 字符串

- console.log(Number('123')); // 123
- onsole.log(Number('abc123')); // NaN
- console.log(Number('')); // 0
- console.log(Number(' ')); //0

2. 布尔值

- console.log(Number(true)); // 1
- console.log(Number(false)); // 0

3. undefined 和 null

- console.log(Number(undefined)); // NaN
- console.log(Number(null)); //0

### 其他类型转换成 Boolean 使用 boolean() 方式

1. 字符串

- console.log(Boolean('')); // false
- console.log(Boolean(' ')); // true
- console.log(Boolean('false')); // false

2. 数字

- console.log(Boolean(0)); // false
- console.log(Boolean(NaN)); // false

3. undefined 和 null

- console.log(Boolean(undefined)); // false
- console.log(Boolean(null)); // false
- console.log(Boolean({})); // true
  **总结: NaN 0 undefined null '' 这五种转换为 false,其余 都是 true**
  **强调 ,涉及到隐式转换时 所使用的都是 String() Number() Boolean() 方式**

## js 运算符

- js 运算包含 +(加)-(减)\*(乘)/(除)%(取模)
- 非数值进行加减乘除取余时,会先转换成 数字类型 (隐式转换) Number()
- **任何值和 NaN 做运算的结果都是 NaN。**
- 任何的值和字符串做加法运算，都会先转换为字符串，然后再做拼串操作。console.log('11' + 1); // 111
- **任何值做-、\*、/运算时都会自动转换为 Number。**

## js 的自增自减

- ++a 是 先++再赋值 (返回的结果 是 +1 之后的值).
- a++ 是 先赋值 后++ (返回的结果 是 +1 之前的值).
- --a 是 先-- 再赋值 (返回的结果 是 -1 之后的值).
- a-- 是 先赋值 后-- (返回的结果 是 -1 之前的值).
- 主要作用就是实现自增或者自减

## js 的比较运算符

- 有 > < >= <= == != ===(严格等于) !==(严格不等于).
- 比较运算符 通过返回 true 或者 false 来表明比较的结果.
- 非数值的比较 会将其转换为数字然后再比较.
- 任何值和 NaN 做任何比较都是 false.
  **特殊 两边都是字符串 不会将其转换为数字进行比较。而是比较 unicode 编码.**
- 严格等于 先比较数据类型,再比较大小.
- console.log(3 > 5); // false
- console.log(3 <= 5); // true
- console.log(true > 0);//true
- console.log(10 < '100'); // true
- console.log(10 > 'hello'); // false
- console.log('123' > '59'); // false
- console.log('hello' > 'world'); // false
- console.log(5 == '5'); //true
- console.log(undefined == null); // true
- console.log(NaN == NaN); //false
- console.log(5 === '5'); // false
- console.log(undefined === null); //false

## parseInt 和 parseFloat

- parseInt 是转换整数的
- parseFloat 是转换小数的
- parse 表示“转换”，Int 表示“整数” ， Float 表示"小数".
- **转换规则: 从第一个非空白字符（空格、换行、tab）开始转换，直到遇到一个非数字字符为止。取整数 不会四舍五入**
- 如果对不是字符串的使用 parseInt 或者 parseFloat 的话 会将其先转换为 String 在进行操作.
- parseInt 结果： 
  - var a = '12345'; console.log(parseInt(a)); // 12345 
- parseFlaot  结果： 
  - var b = '123.4'; console.log(parseFloat(b)); // 123.4 
- 字符串带字母： 
  - var  c = '123a'; console.log(parseInt(c)); // 123 
  - console.log(parseInt(' 2019abc')); // 2019 
- parseInt相加的结果： var sum = parseInt(5.8) + parseInt(4.7); //console.log(sum); // 9 
- parseFloat小数加字母结果： var d = "123.456px"; console.log(parseFloat(d)); //123.456


## JS 中的常用对象与计算方式

- Date 对象 调用 Date 这个对象需要 new 出来一个实例对象函数 可以获取日期 时间 如:年月日 时分秒 毫秒 时间戳 等.
- Math 对象 数学中常用的工具不需要 new 只需要直接使用这个工具就行.
  - 可以向上取整 向下取整 求取最大值 最小值 获取绝对值 幂指数 开方 四舍五入 随机数等常用操作
- 逻辑运算符.
  - 一是 && 且 当两边的数据判断结果都是正确的时候 返回的结果就是 true 其他情况都是 false.
  - 一是 || 或 当两边的参数判断结果都是 false 的时候 返回的结果就是 false 其他情况 都是 true.
  - 一是 ! 非 取反 在参数前面加上 ! 时 true 会变成 false / false 会变成 true.
    **需要记住的时短路运算&& 的短路运算就是当&& 第一个判断结果就是 false 的话就不去判断第二个检测的结果 || 的短路运算就是 当第一个数据为 false 的时候 会去检测第二个值得运算结果 如果是对的就会返回 true 如果两边都是错的那就会返回 false.**

## JS 的顺序结构

1. 选择结构

- if(){} 条件判断语句.
- if(){}else if(){} 条件分支语句 (也称为跳楼现象) 每一条语句都是一种选择.
- if 语句的嵌套 if 代码块中写 if 判断.
- switch(){case 1: 内容 break;} 语句 结合 case 使用 switch()小括号里面写条件 然后下面 case 里面写语句 判断上面 switch 里面的 结果跟 case 里面的那个结果(答案)相匹配;匹配后 break 退出 并输出结果.

2. 循环结构

- for(var i=i0; i<xx.length;i++){代码块} for 的结构样子 适用于重复输出的语句 for(里面的条件要写清楚).
- for 循环嵌套 外层循环一次 里面会相应的循环若干遍(根据写的长度来判断的).
- while(){}和 do{}while()循环 他们 两个也都是循环语句 使用的程度相对于 for 循环而言使用率较低.while 循环先判断在执行 如果 判断不通过 不会执行 或者是死循环. do{}while() 循环是先执行一遍不看条件 第二次循环如果 条件没有达到执行的要求,也不会执行.

## JS 的字符串方法

- var str = "how are you? and you?";
- str.charAt(5); //r 返回指定位置的字符是什么(从 0 开始).
- str.charCodeAt(5)//114 返回指定位置的字符的 Unicode 编码.
- str.indexOf('0')// 1 返回 o 在字符串中的位置.
- str.lastindexOf('0') //18 返回 o 在字符串的位置(从后往前).
- str.concat(str2)// 拼接字符串 组成新的字符串.
- str.slice(1,6)//'ow ar' 截取在数值范围的字符串.(起始位置,结束位置)结束位置-1 就是实际的取值效果.
- str.substr(1,6)//'ow are' 第一位数是开始位置 第二位数是截取的位数是多少.
- str.toLowerCase() //把大写字母变成小写 .
- sre.toUpperCase() //把小写字母变成大写 .
