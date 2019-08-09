# function 函数
## function函数的创建方式
1. 第一种方式 function 关键字
- function fun(){} 关键字 function 函数名 () {} 组合而成
2. 第二种方式 函数表达式
- var fun = function(){} 没有 函数名 直接赋值给一个变量
3. 立即执行函数(自执行函数)
- ;(function(){})() 在创建的时候就会执行一次 然后就不执行了
**函数命名的方式与变量的命名方式一样 函数只有调用的时候才会有用 不调用是不会执行的 执行方式 就是: 函数名() 就可以执**
## function的形参
1. 函数名后面的小括号里面可以写参数.称之为 形参 占位用 没有调用之前就是 undefined
2. 函数名(a);a 代表参数. 函数名()中的 a 就是实参 在 函数名(a) 的时候 会把实参值赋给形参 然后 通过函数内部返回结果
3. 正常情况下 实际参数与形式参数的个数要相同. 多个形参之间要是用 , 隔开(形参类似于起了变量的名字 只是没有赋值而已)
## function 函数的 return 返回值
```html
  1 function sum(a, b) {
  2 return a + b; 
  3 console.log(a + b); 
  4 } 
  5  var num = sum(1, 3);
  6  console.log(num); // 4 }
```
- 第一行 函数 sum 中有两个形参 a b 
- 第二行会把 a + b 的和给返回出来
- 对于上面的代码就是 把 a+b 的结果返回出来. 并且 下面第 3 行代码永远也不会执行 
- 对于第 5 行来说就是把 a b 的实参值给了形参然后结果返回在 赋值给了 变量 num 所以num这个变量的值可以参与其他的运算等操作  
## JS function函数的作用域
### 作用域分为 全局作用域 和 局部作用域(也叫函数作用域)
 - 作用域 : 就是变量的作用范围 (所谓的全局是就是在 script 标签下 )
 - 全局作用域 就是变量在全局范围中 在页面的任何位置都可以使用 可以访问的到.
 - 局部作用域  就是变量在 函数内部声明的 只能在局部使用不能再全局范围使用 
 - 局部作用域之间不能互相访问
 ```html
 	<script>
     //----全局作用域
     function foo() {
				//--- 局部作用域
      }
      // ---- 全局作用域
    function say() {
				var b = 20; //--- 局部变量
        console.log(b); // 20
        //----局部作用域
      }
      //---全局作用域
  </script>
 ```
- 函数内部声明的变量 只能在其内部使用 其他的不能使用  
- 变量的查找规则 就是 就近原则 如果在 自身找不到 就直接会向上一级进行查找. 直至到全局 范围  如果全局范围也没有那就会报错
- 在函数中 要访问 全局对象可以使用 window.变量名 进行使用
## function 函数变量和函数的声明提升
- function函数存在 声明提升(提升script 全局下的顶部)
- 所以 function 声明的函数可以 先使用后声明在 由上至下执行的语句中 执行语句可以放在 函数的上面  

```html
  say();
  function say() {
            alert('你好');
            write();
    }
```
```html 
  1  console.log(a); // undefined 说明变量存在
  2  var a = 10;
  3  var a;
  4  console.log(a);
  5  a = 10;
```
- 变量也存在 提升 在下面的代码中 1 的执行结果为 undefined 所以 说明 a 存在 只是没有被赋值而已
- 所以 把 1  2 的执行结果 分解成 3 4 5 就是执行的顺序第 5 步赋值不会提升 
- 在函数 局部作用域中也存在 声明提前的 特性
## function 的参数传递问题
- 原始的基本数据类型 在作为参数传递时 不会改变原来的数据 
- 打印 原始数据 和 打印修改后的值是 会发现 发现 原始数据不会改变
- 引用的数据类型作为参数传递时 会影响数据
- 打印 原始数据 和 打印修改后的数据是 会发现 原始值会发生改变
### 函数中的递归思想 
1. 后面的数据 要跟前面的数据有关联 才能用到递归 
2. 递归的运算对比for 循环 会更加占内存
3. 递归 一定要有 跳出的条件 要不然 就会报错
```html
   // 求阶乘
    function jc(n) {
          if (n === 1) {
                return 1;
          }
          return n * jc(n - 1);
      }
    console.log(jc(5)); // 120

    //求阶乘和   要用到上面的函数
     function jch(n) {
            if (n === 1) {
           return 1;
        }
          return jc(n) + jch(n - 1);
      }
    console.log(jch(4));

    // 斐波那切数列(不死神兔)
    function fb(n) {
            if (n === 1 || n === 2) {
                return 1;
            }
            return fb(n - 1) + fb(n - 2);
        }
    console.log(fb(12));

    // 台阶问题 每次走1 或者2   走上第 10 阶  有几种走法
    function foo(n) {
            if (n === 1 || n === 0) {
                return 1;
            }
            return foo(n - 1) + foo(n - 2);
        }
    console.log(foo(3));

    //数组的翻转
    <script>
        var arr = [1, 3, 5, 7, 9];
        // 两两交换
        function reverse(arr) {
            var len = arr.length;
            for (var i = 0; i < len / 2; i++) {
                // arr[i] 和 arr[len-i-1] 交换
                var temp = arr[i];
                arr[i] = arr[len - 1 - i];
                arr[len - 1 - i] = temp;
            }
        }
        reverse(arr);
        console.log(arr);

        var arr2 = [2, 4, 6, 8, 10];
        function reverse2(arr) {
            var tempArr = [];
            for (var i = 0; i < arr.length; i++) {
                tempArr.unshift(arr[i]);
            }
            return tempArr;
        }
        console.log(reverse2(arr2));
    </script>

    //求某年某月某天 在那年是第几天
        <script>
        // 2018年9月3日;
        var date = new Date('2018-09-03');
        var year = date.getFullYear();
        var month = date.getMonth();
        var day = date.getDate();
        var monthArr = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
        // console.log(year, month, day);
        var totalDay = 0;
        for (var i = 0; i < month; i++) {
            totalDay += monthArr[i];
        }
        totalDay += day;
        if (year % 4 === 0 && year % 100 !== 0 || year % 400 === 0) {
            // 是闰年 并且 超过2月
            if (month > 1) {
                totalDay++;
            }
        }
        console.log(totalDay);
    </script>
```