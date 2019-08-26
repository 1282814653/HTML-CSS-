## JS 对象的分类

1. Js 内置对象 Array Object Math 等.
2. 宿主对象 BOM 和 DOM console 等.
3. 开发人员自定义的对象. ###对象的意义
4. 对象是用来封装数据信息,用来描述一个事物.
5. 对象由 属性名.属性值(键值对组合) ,也可以是个集合.
6. 对象具有属性(特征,一般是静态的)和方法(行为, 一般为动态的) .
7. 对象之间用 , 逗号 隔开书写.

## 对象的创建方式

1. 字面量形式.

- var obj = {};

2. 通过 Object 这个顶级对象 new 一个对象.

- var obj = new Object();

3. 自定义一个构造函数 new 一个对象 .

- function Person(形参可有多个){ 代码} ;
- 调用 var zz = new Person(填写实参内容);
- 注意: 构造函数书写时首字母大写 构造函数同时要用 New ;

### 对象的增删查改

1. 增加 .

- 变量名.属性 = 参数 如 obj.name = "寒冰";

2. 修改.

- 变量名.属性 = 参数 如 obj.name = "木木"; 上面的寒冰就会变成木木.

3. 删除.

- delete 变量名.属性 如 delect obj.name name 这个属性就不存在了.

4. 查询.

- 直接打印 变量名.属性名.
  **引用数据类型的赋值是把这个变量名的地址赋值过去的**

### this 的指向问题

- 分为两种情况 普通函数 与 构造函数.
- 普通函数中的 this 指向的是调用者 谁用就指向谁.
- 构造函数中的 this 指向的是 new 出来的那个实例对象 .

### 遍历对象

- for(var key in obj ){代码}.
- 如果打印输出 key 输出的是这个对象的 属性名.
- 如果要拿到属性值与名字时 就必须使用 obj[key] 方式 来获取 ([]方式获取参数).

## JSON 的使用方法

- JSON 是一种轻量级的数据交换格式
- JSON 是 js 对象的字符串表示方式 是使用文本表示一个 JS 对象信息的 本质上是一个字符串.
- 对象 数组这些 数据是没有办法进行传输数只有文本可以进行 传输

```html
<script>
  var movie = {
    title: "我不是药神",
    casts: [
      {
        name: "徐峥",
        avatar: "http://xxxx.jpg",
        age: 45
      },
      {
        name: "黄渤",
        avatar: "http://xxxx2.jpg",
        age: 42
      }
    ],
    pubDate: "2017-10-1",
    rate: 5
  };
  // 想把movie 保存的数据 传给后台,name 需要 把对象转换为字符串
  var jsonStr = JSON.stringify(movie);
  console.log(jsonStr);
  // json字符串
  // '{"title":"我不是药神","casts":[{"name":"徐峥","avatar":"http://xxxx.jpg","age":45},{"name":"黄渤","avatar":"http://xxxx2.jpg","age":42}],"pubDate":"2017-10-1","rate":5}'
  // 相对数据的增删改查,需要要把传过来的文本json字符串  变回对象
  var jsonObj = JSON.parse(jsonStr);
  // 只有json 字符串  才能变回对象
  console.log(jsonObj);

  // '{name:"张三"}'
  // 普通字符串 变不回对象
  console.log(JSON.parse('{name:"张三"}')); //F

  console.log(JSON.parse('{"name":"张三"}')); //T
</script>
```

```html
<script>
  //对象的创建
  var user = {
    name: "张三",
    age: 26,
    sex: true,
    like: ["篮球", "足球"],
    child: {
      name: "小明",
      age: 2
    },
    say: function() {
      alert("你好");
    },
    sayName: function() {
      // this的 指向 当函数没调用时,this的指向是 不知道的
      // 调用时才会确定
      alert(this.name);
    }
  };
  // 获取对象的属性  对象.属性名;
  console.log(user.name);
  // 调用 user 的  say 方法
  user.say();
  // 调用了.此时 this 指向了  user 对象
  // this 指向调用者 (.前边的那个对象)
</script>
```

```html
<script>
  //对象的遍历
  var obj = {
    name: "张三",
    age: 30,
    sex: "男"
  };
  // 遍历对象
  for (var key in obj) {
    console.log(key); // 这个对象的 所有属性名
    // obj.key  拿到的是 obj的 key 属性( obj 并没有  key属性,所以 undefined)
    // obj.xx 获取属性时,如果 xx 是个 变量(会变化)  需要采用  obj[xx]获取属性值
    console.log(obj.key); // ubndefined
    console.log(obj[key]); // 拿到的是属性对应的值
  }
</script>
```
