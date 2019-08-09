## 三角形的制作

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <style>
      .box {
        width: 0px;
        height: 0px;
        /* background: transparent; */
        margin: auto;
        border: 100px solid;
        /* border-top-color: aqua; */
        border-color: transparent transparent red transparent;
        /* border-right-color: black;
        border-bottom-color: blue;
        border-left-color: yellow; */
      }
    </style>
  </head>
  <body>
    <div class="box"></div>
  </body>
</html>
```

## 实现一个盒子在浏览器垂直居中的几种方法

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <style>
      .box {
        /* 第一种 通过定位 不需要计算宽高 */
        width: 100px;
        height: 100px;
        background: red;
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        margin: auto;

        /* 第二种  通过定位 需要计算宽高*/
        /* width: 100px;
            height: 100px;
            background: red;
            position: absolute;
            top: 50%;
            left:50%;
            margin-left: -50px;
            margin-top: -50px; */

        /* 第三种 通过定位 不用计算宽高*/
        /* width: 100px;
            height: 100px;
            background: black;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%,-50%); */

        /*第四种 通过定位 计算宽高  */
        /* width: 100px;
            height: 100px;
            background: orange;
            position: absolute;
            top: calc(50% - 50px);
            left:calc(50% - 50px); */

        /* 第五种  */
        /* width: 100px;
            height: 100px;
            background: palegreen;
            margin:50% auto;
            transform: translateY(-50%); */
      }
    </style>
  </head>
  <body>
    <div class="box"></div>
  </body>
</html>
```
