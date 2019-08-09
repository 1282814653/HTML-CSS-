# JS数组
## 数组的基本操作
- Array() 是 js 的内部对象 
- 可以通过 数组名[]([]里面写元素下标来获取数组的那个下标的数据) 下标 获取数据.数组中每个元素都有相应的下标 .
- 数组中的数据 可以是任何的数据类型 在同一个数组中不一定是同一类的数据类型 但是数组通常用来表示同一种数据类型.
## 数组的创建
1. 可以通过 字面量形式 如 var arr = [12,3,4,5]; 来创建数组 但是相应的创建出来的数组都是死数据.
2. 可以通过 new 来实例化一个对象 创建一个数组如 var arr = new Array(); 来创建一个数组.这样的数组具有灵活性 Array() 的小括号里面可以设置参数 .当写一个数字的时候 是限定里面可以写多少个数组 相当于数组的长度 如果里面的参数大于等于两个的时候 里面写的就是数组了 .
3. 数组中的某个元素的添加
- 可以通过数组的下标进行添加 如 arr[20] = 5; 就会在下标是 20 的位置上添加一个 数字 5 (前提是下标 20 的这个位置是个空的位置)
4. 数组中的某个元素的查找
- 通过下标来查找那个元素的数据 如 arr[20] 就会返回 数字 5
5. 数组中某个元素的修改
- 选中那个数组的下标 如 arr[20] = 10 ; 打印出来原先的数字 5 就会变成数字 10 了 通过数组下标修改元素
6. 数组的长度 是通过 数组名.length 来获取的
- 数组的长度是从 0 开始查询的所以 数组的总长度就是 .length-1 就是数组的总长度
7. 数组的修改
- 如果要修改数组的长度 大于当时的数组的长度是 会多出一部分 位置 但是没有数据 所以会显示 null 空 . 如果修改的数据 小于当时的数据 则会删除 原先的数组的长度 数组将会从后往前删除 那些多余的数组.
## 数组的基本操作方式
1. 删除的两种方式
- pop()删除 是删除的数组的末尾 如果 console.log(数组名.pop()) 怎会弹出 删除的那个数的 信息
- shift() 删除 是删除数组的开始 如果 console.log(数组名.shift()) 怎会弹出 删除的那个数的 信息
2. 添加的两种方
- push() 添加 添加的位置是数组的末尾 如果 console.log(数组名.push()) 则会输出数组的长度
- unshift() 添加 则是添加到数组的开始位置 console.log(数组名.unshift()) 则会输出数组的长度
3. join() 将数组转换为 字符串 返回结果 为转换后的字符串(不会改变原来数组的值)/ join() 可以指定一个字符串为参数 (用来分割 前后两个数据) 这个字符串将会成为数组中的连接符 如果不指定这个参数就会使用默认的连接 作为连接符
4. spilt() 可以将字符串转换为数组 转换的数组(不会改变原来的字符串) () 中可以指定 参数来分割字符串 新的数组 = 原来的字符串.spilt(分隔符,数组长度)
5. concat() 用来连接两个或者两个以上的数组,返回一个新的数组 (不会改变原来的数组 )
## 数组的高级使用
1. forEach() 数组遍历
- 属性名.forEach(function(参数一, 参数二, 参数三){})
- forEach() 方法可以遍历数组 
- ()里可以写一个函数 参数一元素为 item . 参数二元素为 index . 参数三就是要遍历数组的名字.
- 第一个参数 item 必须写 后面两个可以省略
```html
<script>
    var arr = [1, 3, 5, 7, 9];
    arr.forEach(function(item,index, arr){
        console.log(item);
        console.log(index);
        console.log(arr);
    })
</script>
```
2. reverse() 翻转数组
- var arr = [1,2,3,4,5,6];
- var ar = arr.reverse(); //修改了原数组
- console.log(ar); //返回值是 反转后的数组
- console.log(arr); 
3. slice 截取数组
- var arr = ['a','s','d','e','f'];
- var result = arr.slice(1,3);
- resule = ['a','e','f']
- arr.slice(起始索引,结束索引(不包含结束的索引));
- 如果只有一个其实索引的话 你就是截取到最后
- 截取的结果不会影响原数组 arr还是原来的值 但是resule 的值就会发生改变
4. splice() 替换或者删除数组中的元素
- var arr3 = ['a', 'b', 'c', 'd', 'e'];
- ()里两个参数 第一个为索引起始位置, 第二个为你要替换的位数(替换几位)
- arr3.splice(1,2,10);
- 那么 arr3 就会变成['a', 10, 'd', 'e'] //修改了原数组
- 如果只写 开始索引结束索引 不写 替换数值的话 那就是删除操作
- arr3.splice(3,1);从第 3 位开始 删除 1 位
5. indeOf() 和 lastIndexOf() 返回元素在数组中的索引
```html
<script>
  var arr4 = ['a', 'b', 'b', 'd', 'e'];
    var index1 = arr4.indexOf('b'); // 1  从前往后匹配
    var index2 = arr4.lastIndexOf('b'); // 2  从后往前匹配
    var index3 = arr4.indexOf('f'); // 匹配不到 返回 -1;
    console.log(index1);
    console.log(index2);
    console.log(index3);
</script>
```
- indexOf 返回的是从前往后匹配 但是下标还是从前开始计算
- lastIndexOf 返回的是从后往前匹配  下标也是从前往后算起
- 如果匹配不到数据 那就返回-1 说明没有这个数据
6. sort() 排序
- 正常情况 都是安装 unicode 编码来排序 
- var arr = ['e', 'c', 'a', 'b']; //排序后['a','b','c','e']
- var arr = [ 1,2,3,11,23] //排序后[1,11,2,23,5] 按照编码排的
**总结: 不带参数时 就按照Unicode来排序**
- 带参数时可以指定排序规则
```html
<script>
    arr2.sort(function (a, b) {
        // a,b 代表 arr2 里边相邻的两个元素
        // 指定排序规则
        return a - b; // 从小到大 升序
        // 结果<0  位置不变
        // 结果>0  交换位置
        // 等于0  不动
        // return b - a; // 从大到小  降序
        })
        console.log(arr2);
        var users = [{
                name: '张三',
                age: 20,
                height: 176
            },
            {
                name: '李四',
                age: 19,
                height: 175
            },
            {
                name: '王五',
                age: 22,
                height: 172
            },
            {
                name: '赵六',
                age: 18,
                height: 174
            },
            {
                name: '陈琦',
                age: 18,
                height: 178
            },
        ]
        // 按照年龄从小到大排序
        // 年龄相同时  按身高从大到小排
        users.sort(function (a, b) {
            if (a.age === b.age) {
                return b.height - a.height
            } else {
                return a.age - b.age;
            }
        })
        console.log(users);
    </script>
```


## 数组的案例演示
```html
<script>
  //数组的平均数
  var arr = [1, 22, 3, 47, 5, 16, 7, 331, 9, 10];
  // 求证数组的平均数
  // 先对数组元素  求和
  var sum = 0;
  for (var i = 0; i < arr.length; i++) {
    // sum = sum + arr[i];
    sum += arr[i];
  }
  // console.log(sum);
  var arg = sum / arr.length;
  console.log(arg);
</script>
```
```html
<script>
  //数组的冒泡排序
  var arr = [23, 45, 12, 9, 47, 11];
  for (var j = 1; j < arr.length; j++) {
    // 外层 for 循环 控制 轮次
    for (var i = 0; i < arr.length - j; i++) {
      // 内层 for 循环  负责 找出本轮最大值
      if (arr[i] > arr[i + 1]) {
        // 顺序错误
        // 交换位置
        // 先把之前arr[i]的值保存下来
        var temp = arr[i];
        arr[i] = arr[i + 1]; // arr[i]已经发生了改变
        arr[i + 1] = temp;
      }
      // console.log(arr);
    }
    // console.log(arr);
  }
  console.log(arr);
</script>
```
```html
<script>
  //数组找因数
  var num = parseInt(prompt("请输入一个整数"));
  var count = 0;
  // 计数器,用来记录因数的个数
  for (var i = 1; i <= num; i++) {
    if (num % i === 0) {
      console.log(i);
      count++;
    }
  }
  console.log(count);
</script>
```

```html
<script>
  // 978 水仙花数
  for (var i = 100; i < 1000; i++) {
    // 获取个位数
    var ge = i % 10;
    // 十位
    var shi = Math.floor(i / 10) % 10;
    // var shi = parstInt(i%100/10);
    // 百位
    var bai = Math.floor(i / 100);
    if (Math.pow(ge, 3) + Math.pow(shi, 3) + Math.pow(bai, 3) === i) {
      console.log(i);
    }
  }
</script>
```

```html
<script>
  //  求阶乘
  var jc = 1;
  for (var i = 1; i <= 6; i++) {
    jc = jc * i;
  }
  console.log(jc);
</script>
```

```html
<script>
  //判断质数
  var num = parseInt(prompt("青输入一个整数"));
  // 1 . 因数个数 2个
  // var count = 0;
  // for (var i = 1; i <= num; i++) {
  //     if (num % i === 0) {
  //         count++;
  //     }
  // }
  // if (count === 2) {
  //     alert(num + '是质数');
  // } else {
  //     alert(num + '不是质数');
  // }
  var isZhi = true;
  for (var i = 2; i < num; i++) {
    if (num % i === 0) {
      // 碰到了其他因数,说明不是质数
      isZhi = false;
      break;
    }
  }
  isZhi ? alert("是质数") : alert("不是质数");
</script>
```

```html
<script>
  // 选择排序
  var arr = [11, 9, 3, 6, 2, 0];
  // 优化
  // 外层循环控制轮次
  for (var j = 0; j < arr.length - 1; j++) {
    // 本轮待排序元素的 开头位置
    var minIndex = j;
    for (var i = j + 1; i < arr.length; i++) {
      if (arr[minIndex] > arr[i]) {
        minIndex = i;
        // 交换下标
      }
    }
    // 经过这样一轮比较  咱们就找到了 最小值 对应的 下标
    // 交换位置
    var temp = arr[j];
    arr[j] = arr[minIndex];
    arr[minIndex] = temp;
    // console.log(arr);
  }
  alert(arr);
</script>
```

```html
<script>
  //插入排序
  var arr = [24, 34, 21, 9, 8];
  for (var i = 0; i < arr.length; i++) {
    var temp = arr[i];
    //方式一
    // for (var j = i - 1; j >= -1; j--) {
    //     if (temp < arr[j]) {
    //         arr[j + 1] = arr[j];
    //     } else {
    //         arr[j + 1] = temp;
    //         break;
    //     }
    // }
    //方式二
    var j = i - 1;
    while (temp < arr[j] && j >= 0) {
      arr[j + 1] = arr[j];
      j--;
    }
    arr[j + 1] = temp;
  }
  console.log(arr);
</script>
```


 
