# JS 事件

## DOM

1. HTML DOM 是 HTML Document Object Model(文档对象模型) 的缩写.DOM 是专门适用于 HTML/XHTML 的文本对象模型,熟悉软件开发的人员可以将 HTML DOM 理解为网页的 API ,他将网页中的 各个元素都看作为一个个对象 ,从而使网页中的元素也可以被计算机语言(js)获取或者编辑.
2. DOM 将文档解析为一个有节点对象(包含属性和方法的对象) 组成的结构集合 是 web 网页的完全的面向对象表述,简而言之 将 web 页面和脚本或程序语言连接起来,它能够使用如 javaScript 等脚本语言进行修改.
3. DOM 是载入到浏览器中的文档模型 是以节点的形式变现文档,每个节点代表文档的构成部分(如 页面元素 字符串 注释等等).
4. 在 HTML 中一切都是节点
   - 整个文档就是一个文档节点 .
   - 每个 HTML 就是一个元素节点. (标签)
   - 标签中的文字则是文字节点.(文本)
   - 标签的属性就是属性节点.(属性)

### JS 是事件驱动为核心的一门语言.js 是采用事件驱动响应用户操作的.

1. 通过鼠标或者按键在浏览器窗口或者网页元素上的执行操作 称之为事件.
2. 由鼠标或者热键引发的一连串程序的动作 称之为事件驱动
3. 对事件进行处理程序或函数 称之为事件处理程序

### 事件有三要素

**事件源 事件 事件驱动程序**

1. 事件源: 要触发的对象.
2. 事件: 怎么执行这个事情.
3. 事件处理程序: 发生了什么事情.
   **Js 就是要获取事件源 绑定事件 书写事件驱动程序**

### DOM 节点的获取方式

1. 通过 id 准确获得 id 而且 id 也是唯一
   - document.getElementById('id 名字');
2. 通过标签名(元素)获取 因为获取的是数组所以要在后面加上下标是哪一位.
   - document.getElementsByTagName("标签名字")[0];
3. 通过 class 类名获取 跟元素一样都是获取的是 数组 所以在后面要要加上是那个元素或者不加 在处理添加事件的时候在指明是哪个元素.(在 IE 5 6 7 8 中使用无效)
   - document.getElementsByClassName('class 名字');

#### 获取 DOM 节点

1. 通过父节点 一个元素就一个父节点
   - parentNode
2. 通过兄弟节点 不过存在兼容问题 - nextSibling(IE 7 8 9 指的是第一个元素节点(标签注释)在火狐 谷歌 IE9(标准)以后的都是指下一个节点包含空文档和换行节点) - nextElementSibling (在火狐 谷歌 IE9 中都是指下一个元素节点)
   **this.nextElementSibling || this.nextSibling 兼容的写法**
3. 单个子节点
   - firstChild(在 IE 6 7 8 中指得是第一个元素节点,在火狐 谷歌 IE9+ 以后都是指得第一个节点 包含空文档和换行节点)
   - lastChild(IE 6 7 8 指最后一个元素节点 在火狐 谷歌 IE9+ 以后是指最后一个节点)
   - firstElementChild 在火狐 谷歌 IE9 都是指第一个元素节点
   - lastElementChild 在火狐 谷歌 IE9 都是指最后一个元素节点
4. 所有字节点
   - childNodes 标准属性 它返回指定元素的子元素集合 包含 HTML 节点 所有属性 文本节点 火狐 谷歌 等高版本 会把 换行也会当成子节点
     **nodeType == 1 表示元素(标签)节点**
     **nodeType == 2 表示属性节点**
     **nodeType == 3 表示文本节点**
     **nodeType == 8 表示注释节点**
   - children 非标准属性 它返回的是指定元素的子元素集合 他只返回 HTML 节点 不返回文本节点 在 IE 6 7 8 中包含 注释节点 在 IE 6 7 8 注释节点不要写在前面 在写兼容的时候 ..但是它和 innerHTML 方法一样得到了所有的浏览器的支持.

## DOM 节点的操作

1. 创建节点
   - document.createElement();
2. 插入节点(两证方式)
   - 父节点.appendChild();
   - 父节点.insertBefore();(两个参数第一个插入元素 第二个在那个元素之前 如果第二个不写 那么效果与上面的插入效果一样)
3. 删除节点
   - 父节点.removeChild(子节点);
   - 如果需要自己删除自己的话 node.parentNode.removeChild(node);
4. 复制节点
   - 源节点.cloneNode(true);
   - 方法内可以传参 true 深层赋复制(复制所有) 如果是 false 的话 值赋值节点(元素)自身,不会复制里面的内容 .
5. 节点属性的设置
   - 获取: getAttribute(名称);
   - 设置: setAttribute(名称,值);
   - 删除: removeAttribute(名称);

## DOM 的 内容修改

1. value 只针对表单有效 是属性
2. innerHTML 插入可执行的标签 标签和样式会被解析 常用于生成动态页面
3. innerText 插入文本内容 样式和标签都会被当做文本内容处理

## DOM 事件

| 属性        | 事件                         |
| ----------- | ---------------------------- |
| onload      | 某个页面或图像被完成加载     |
| onblur      | 元素失去焦点                 |
| onfocus     | 元素获得焦点                 |
| onchange    | 用户改变域的内容             |
| onclick     | 鼠标单击某个对象             |
| ondblclick  | 鼠标双击某个事件             |
| onmouseover | 鼠标移入到某个元素身上       |
| onmouseout  | 鼠标从某个元素身上移出       |
| onabort     | 图像加载被中断               |
| onerror     | 当加载文档图像时发生某个错误 |
| onkeydown   | 某个键盘的键被按下           |
| onkeypress  | 某个键盘的键被按下或者摁住   |
| onkeyup     | 某个键盘的键被松开           |
| onmousedown | 某个鼠标按键被按下           |
| onmousemove | 鼠标被移动                   |
| onmouseup   | 某个鼠标被按键松开           |
| onreset     | 重复按钮被点击               |
| onresize    | 窗口或框架被调整尺寸         |
| onselect    | 文本被选定                   |
| onsubmit    | 提交按钮被点击               |
| onunload    | 用户退出页面                 |

## H5 类名的操作

1. 添加 add

- DOM 元素.classList.add("类名");//..多个类名之间用逗号隔开

2. 删除 remove

- DOM 元素.classremove('类名');

3. 判断类名是否存在 contains 存在返回 T 不存在 返回 F

- DOM 元素.classList.contains('类名);

4. 根据 DOM 元素的下标返回类名 item

- DOM 元素.classList.item(下标);

5. toggle 查看 class 类名是否存在 有则删除 无则添加

- DOM 元素.classList.toggle("类名");

## DOM 节点的增删改查

**不论操作哪个节点都需要先找到节点然后在执行操作**

1. 创建节点

- documen.createElement("标签名");

2. 插入节点 两种方式

- 父节点.appendChild(新的子节点);
- document.body.appendChild(变量名);
- 这是在父节点的最后插入一个新的子节点
- 分 ------------ 割--------------线
- 父节点.insertBefore(新的子节点,参考的子节点);
- 在参考节点前插入新的节点.如果参考节点为 null 那么就在他的父节点最后插入子节点
- document.body.insertBefore(插入的节点变量,插入节点是哪个);
  **重复插入同一个节点 那么只会保留一个**

3. 删除节点

- 父节点.removeChild(子节点);
- 使用父节点删除子节点 必须要指定删除哪个子节点
- document.body.removeChild(子节点);
- 自己删除自己
- node1.parentNode.removeChild(node1);

4. 复制节点

- 节点名.cloneNode(); //浅复制只复制标签名
- 节点名.cloneNode(true);//深复制 标签还有里面的内容都复制

### arguments 参数

- arguements 是实参对象 只能在函数内部使用

```html
<script>
    function(s,y,x){
      console.log(arguments); //类数组对象
      console.log(arguments.length); // 3
      console.log(arguments[0]); // 根据下标返回 对应的内容
      console.log(arguments.callee); // 调用函数本身
      return s+y+z;
    }
  add (1,2,3);

  //arguments.callee 实际应用
  function fn(n){
      if(n==1|| n==2){
        return 1;
      }
    return argument.callee(n-1)+arguments.callee(n-2);;
  }
  console.log(5);
</script>
```

### addEventListener 事件监听的方法

1.  添加 addEventListener 事件

- 允许给一个事件添加多个 listener .
- 提供了一个更精细的手段 控制 listener 的触发阶段 (选择捕获或者冒泡).
- 对任何的 DOM 元素都效果 而不仅仅只针对 html 元素有效.
- 语法 : target.addEventListenter(type,listener,iscapture);
- target : 文档节点 document window XMLHttpRequest(事件源) .
- type : 字符串型的 事件名称 不包含 on 直接写成 'click','mouseover' 就行.
- listener : 函数 要实现 EventListener 接口或者是 JavaScript 中的函数.
- isCapture : 是否使用捕捉 一般是 false.
- 如: aa.addEventListener('click',function foo(){},true/false);//内部函数-内部事件
- 如 : aa.addEventListener('click',foo,false);
- function foo(){} //外部函数- 外部事件

2. 移出绑定事件 removeEventListener

- 如果 同时监听一个事件 那么分别为 '事件捕获'和'事件冒泡'一共两次.对两个事件分别移除.两者不会互相干扰
- 移除的事件必须是外部事件

3. 兼容性处理(关于浏览器低版本 和高版本的处理)

- function myAddEventListener(el, type, fun){
- //arrachEvent() 是 ie 的专用方法
- if(ele.attachEvent){//判断浏览器是否支持低版本
- ele.attachEvent('on'+type,fun);
- }else{
- ele.addEventListener(type,fun); // 高版本
- }
- }
- // ele 绑定的元素
- // type 事件类型 带不带 on
- // fun 执行的方法

## 定时器

1. setTimeout() 延迟执行

- 只执行一次

2. setInterval() 循环执行

- 可以执行多次 要设置 清除循环

3. clearInterval() 清除循环
