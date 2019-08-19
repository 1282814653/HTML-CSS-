# jquery 的使用方式

**jq 使用前要先引入这个 js 文件**

1. jq 的元素获取

- \$('.calss/#id/标签名')
- 如 : \$('.box') 获取 class 为 box 元素
- 获取事件源的 基本选择器 同 css 选择一样

2. jq 与 js 之间的转换

- \$('.box[0]') 就是把 jq 对象转换为 js 对象
- 通过 js 获取到元素名字以后 直接在元素前面加上 \$ 即可

3. js 与 jq 的区别

- 事件类型前面不需要加 on
- \$('.box').'click'(function(){}); 直接在事件中写事件函数

4. js 与 jq 的入口函数区别

- js 需要等待 图片加载 jq 不需要等在图片加载

## jq 的选择器

**jq 的选择器与 css 的选择器都是一样的**

1. 其他选择器
   - > 子代选择器
     - \$('.box>.w-box').css('color', 'blue');
   - - 紧邻选择器 紧挨着下边的兄弟元素
       - \$('.active+li').css('fontSize', '24px');
   - ~ 兄弟选择器 后面所有的兄弟
     - \$('.active~li').css('background-color', 'orange');
2. 属性选择器
   - \$('a[href]').css('color', 'red');
   - \$('a[href="baidu"]').css('color', 'green');
   - \$('a[href="baidu"][title]').css('color', 'yellow')

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <style>
      .box > .w-box {
        color: red;
      }

      .li-item.active + li {
        color: red;
      }

      .li-item.active ~ li {
        color: red;
      }
    </style>
  </head>

  <body>
    <div class="box">
      <div class="inner-box">
        <div class="w-box">
          w-box
        </div>
      </div>
      <div class="w-box">
        box 里边的 w-box
      </div>
    </div>
    <ul>
      <li class="li-item">li1</li>
      <li class="li-item active">li2</li>
      <li class="li-item">li3</li>
      <li class="li-item">li4</li>
      <li class="li-item">li5</li>
      <li class="li-item">li6</li>
      <p>p标签</p>
    </ul>
    <a href="">百度</a>
    <a>百度无href</a>
    <a href="baidu">href为百度</a>
    <a href="baidu" title="百度">href为百度</a>

    <!-- <a href="">百度</a> -->

    <script src="js/jquery-3.4.1.min.js"></script>
    <script>
      // css的选择器  和 jquery 选择器是一样的的

      // 其他css 选择器
      // jquery 也适用
      // 子代选择器
      // 紧邻选择器 紧挨着的下一个兄弟
      // 兄弟选择器 后边的所有兄弟

      $(".box>.w-box").css("color", "blue");
      $(".active+li").css("fontSize", "24px");
      $(".active~li").css("background-color", "orange");

      // 属性选择器
      $("a[href]").css("color", "red");
      $('a[href="baidu"]').css("color", "green");
      $('a[href="baidu"][title]').css("color", "yellow");
    </script>
  </body>
</html>
```

3. 筛选选择器

- \$('li:eq(0)').css('color', 'red');
- \$('li:gt(4)').css('color', 'yellow');
- \$('li:lt(4)').css('color', 'green');
- \$('li:odd').css('color', 'pink');
- \$('li:even').css('color', 'purple');
- \$('li:first').css('background-color', 'red');
- \$('li:last').css('background-color', 'yellow');
- \$('p:empty').css('color', 'red');
- \$('p:contains("不凡")').css('color', 'yellow');
- // 获取被选中的多选框 ,prop()可以获取选中状态,并且修改
- \$('input:checked').prop('checked', false);

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>

<body>
    <ul>
        <li>li1</li>
        <li>li2</li>
        <li>li3</li>
        <li>li4</li>
        <li>li5</li>
        <li>li6</li>
        <li>li7</li>
        <li>li8</li>
        <li>li9</li>
        <li>li10</li>
    </ul>
    <p></p>
    <p>不凡学院</p>

    篮球:<input type="checkbox">
    足球:<input type="checkbox">
    乒乓球:<input type="checkbox" checked>

    <!-- <select name="" id="">
        <option value="">篮球</option>
        <option value="" selected>足球</option>
        <option value="">乒乓球</option>

    </select> -->
    <script src="js/jquery-3.4.1.min.js"></script>
    <script>
        $('li:eq(0)').css('color', 'red');
        $('li:gt(4)').css('color', 'yellow');
        $('li:lt(4)').css('color', 'green');
        $('li:odd').css('color', 'pink');
        $('li:even').css('color', 'purple');
        $('li:first').css('background-color', 'red');
        $('li:last').css('background-color', 'yellow');


        $('p:empty').css('color', 'red');
        $('p:contains("不凡")').css('color', 'yellow');

        // 获取被选中的多选框 ,prop()可以获取选中状态,并且修改
        $('input:checked').prop('checked', false);
    </script>

</html>
</body>
```

### jq 对象修改 css 的样式

1. 单独设置某个样式
   - \$('.box').css('backgroundColor','red');
2. 修改 多个样式的时候 要写成对象的形式 带单位要加引号 不带就不加引号 对于字符串要加引号

- \$('.box').css({
  width : 200,
  height : '200px'
  });

### jq 对象对于 attr() 属性的操作

- \$('img').attr('src');
- 获取 img 元素的 src 属性值
- \$('img').attr('src','路径');
- 获取 img 元素的 src 属性值 然后设置 赋值
- \$('img').removeAttr('alt');
- 删除 img 元素的 alt 这个属性

### jq 对象对于类名的操作

- addClass('类名') 向被选元素添加一个或者多个类
- romoveClass('类名') 从被选元素删除一个或者多个类
- toggleClass('类名') 对被选元素进行添加/删除的切换操作 有则删 无则加
- hasClass() 判断被选的元素是否存在

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <style>
      .danger {
        color: red;
      }
    </style>
  </head>

  <body>
    <p class="txt" title="不凡">不凡学院</p>
    <button>添加danger</button>
    <button>删除danger</button>
    <button>切换danger</button>
    <button>判断是否先存在danger</button>
    <script src="js/jquery-3.4.1.min.js"></script>
    <script>
      //     addClass(); 向被选元素添加一个或多个类
      // removeClass(); 从被选元素删除一个或多个类
      // toggleClass(); 对被选元素进行添加/删除类的切换操作
      // hasClass(); 判断被选元素是否存在类

      $("button:eq(0)").click(function() {
        $("p").addClass("danger");
        $("p").addClass("danger strong");
      });
      $("button:eq(1)").click(function() {
        $("p").removeClass("danger");
      });
      $("button:eq(2)").click(function() {
        // 有则删除  无则添加
        $("p").toggleClass("danger");
      });
      $("button:eq(3)").click(function() {
        console.log($("p").hasClass("danger")); // true 或者  false
      });
    </script>
  </body>
</html>
```

### jq 对象对于内容的操作

- js 对象 innerText 对应 jq 对象 text();
- js 对象 innerHTML 对应 jq 对象 html();
- js 对象 value 对应 jq 对象 val();
- jq \$('').prop(''); //专门来设置选中状态的

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>

  <body>
    <p>不凡学院</p>
    <div class="box">
      <div class="inner-box">
        我是内部盒子
      </div>
    </div>
    <input type="text" value="请输入" />
    <input class="checkbox" type="checkbox" />
    <script src="js/jquery-3.4.1.min.js"></script>
    <script>
      // innerText   和 text()
      // innerHTML  和 html()
      // value  和 val()
      console.log($("p").text());
      $("p").text("今天天气很好"); // 设置文本内容

      console.log($(".box").html());
      $(".box").html("<p>woshiyigep标签</p>");

      console.log($("input").val());
      $("input").val("张三");

      // prop()   $('input').prop('checked')   $('input').prop('checked',false)
      // 专门用来设置选中状态
      console.log($(".checkbox").prop("checked")); // 获取选中状态 true 或者 false
      $(".checkbox").prop("checked", true);
    </script>
  </body>
</html>
```

### jq 关系元素查找

- 下面的都是方法
- eq(index);
- find();
- siblings(); 除了自己以外的所有兄弟节点
- children(); 所有孩子节点
- next(); 下一个兄弟节点
- nextAll(); 后面的所有兄弟节点
- nextUntil();后面的兄弟节点,直到...
- prev();上一个兄弟节点
- prevAll();
- prevUntil();
- parent(); 父节点
- parents(); 所有父节点
- parentsUntil();

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>

  <body>
    <ul>
      <li class="li-item">li1</li>
      <li class="li-item">li2</li>
      <li class="li-item">li3</li>
      <li class="li-item">li4</li>
      <li class="li-item active">li5</li>
      <li class="li-item">li6</li>
      <li class="li-item">li7</li>
      <li class="li-item">li8</li>
      <li class="li-item li9">li9</li>
      <li class="li-item">li10</li>
      <p>今天</p>
    </ul>
    <div class="box">
      <div class="inner-box">
        <p>不凡学院</p>
      </div>
      <p>天气很好</p>
    </div>
    <script src="js/jquery-3.4.1.min.js"></script>
    <script>
      // eq(index);
      // find();
      // siblings(); 除了自己以外的所有兄弟节点
      // children(); 所有孩子节点
      // next(); 下一个兄弟节点
      // nextAll(); 后面的所有兄弟节点
      // nextUntil();后面的兄弟节点,直到...
      // prev();上一个兄弟节点
      // prevAll();
      // prevUntil();
      // parent(); 父节点
      // parents(); 所有父节点
      // parentsUntil();

      // .eq()  jq对象的一个方法
      $("li")
        .eq(0)
        .css("color", "red");
      // find()  查找指定元素的 符合条件的后代
      $(".box")
        .find("p")
        .css("color", "yellow");

      $("ul")
        .children()
        .css("color", "orange");
      $("ul")
        .children("li")
        .css("color", "red");

      $(".li-item.active")
        .siblings()
        .css("background-color", "black");
      $(".active")
        .next()
        .css("color", "#fff");
      $(".active")
        .prev()
        .css("color", "pink");
      // nextAll(); 后面的所有兄弟节点
      // prevAll();
      //查找当前元素之后所有的同辈元素，直到遇到匹配的那个元素为止。
      $(".active")
        .nextUntil(".li9")
        .css("background-color", "pink");

      console.log($(".inner-box").parents());
    </script>
  </body>
</html>
```

### mouseover 和 mouseenter

1. mouseover // 会触发多次
2. mouseenter // 只会触发一次

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <style>
      ul {
        list-style: none;
        width: 100px;
        height: 100px;
        background-color: red;
      }

      li {
        width: 80px;
        height: 80px;
        background-color: yellow;
      }

      a {
        display: block;
        width: 40px;
        height: 40px;
        background-color: pink;
      }
    </style>
  </head>

  <body>
    <ul>
      <li>
        <a href="#">百度</a>
      </li>
    </ul>
    <script src="js/jquery-3.4.1.min.js"></script>
    <script>
      $("ul").mouseover(function() {
        console.log("over");
        // 在其后代元素间进行切换时  也会触发事件
        // 相当于 会触发多次
      });
      $("ul").mouseout(function() {
        console.log("out");
        // 在其后代元素间进行切换时  也会触发事件
        // 相当于 会触发多次
      });
      $("ul").mouseenter(function() {
        console.log("enter");
        // 只会触发一次
      });
    </script>
  </body>
</html>
```
