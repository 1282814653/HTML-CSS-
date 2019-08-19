# jq 动画

**属性里面有两个参数 第一个为 显示的速度也就是时间的快慢(默认速度是 400 毫秒)第二个为 回调函数 指定动画结束后做什么**

- show() 显示
- hide() 隐藏
- slideDown() 下滑动
- slideUp() 上滑动
- slideToggle () 上滑动/下滑动 切换
- fadeIn() 淡入
- fadeOut() 淡出
- fadeToggle() 淡入/淡出切换
- fadeTo() 调节透明度 //第一个参数为 显示时间 第二个为透明度

## jq 自定义动画

1.  \$('元素').animate(styles,speed,easing,callback);

- styles 要执行的动画 css 属性 (必填属性)
- speed 要执行动画的时长(可选属性)//'swing' 先慢后快再慢// 'linear'(线性匀速)
- easing 运动函数 以什么运动方式运行的(可选)
- callback 回调函数 这个函数运行结束后 还有没有其他的动画可执行(可选)

1. styles 必需。规定产生动画效果的 CSS 样式和值。可能的 CSS 样式值（提供实例）：

- backgroundPosition
- borderWidth
- borderBottomWidth
- borderLeftWidth
- borderRightWidth
- borderTopWidth
- borderSpacing
- margin
- marginBottom
- marginLeft
- marginRight
- marginTop
- outlineWidth
- padding
- paddingBottom
- paddingLeft
- paddingRight
- paddingTop
- height
- width
- maxHeight
- maxWidth
- minHeight
- minWidth
- font
- fontSize
- bottom
- left
- right
- top
- letterSpacing
- wordSpacing
- lineHeight
- textIndent
  **注释：CSS 样式使用 DOM 名称（比如 "fontSize"）来设置，而非 CSS 名称（比如 "font-size"）。**

2. speed 可选。规定动画的速度。默认是 "normal"。可能的值：

- 毫秒 （比如 1500）
- "slow"
- "normal"
- "fast"

3. easing 可选。规定在不同的动画点中设置动画速度的 easing 函数。内置的 easing 函数：

- swing
- linear
- 扩展插件中提供更多 easing 函数。

4. callback 可选。

- animate 函数执行完之后，要执行的函数。
- 如需学习更多有关 callback 的内容，请访问我们的 jQuery Callback 这一章。

## jq 动画的停止

1. stop()

- 停止当前正在执行的动画
- 当多个动画同时作用于一个单位上面 那么多个动画就会进入排队后一个必须等起那面的执行完毕

2.  stop(stopAll,goToEnd)

- stopAll 是否全部停止 默认为 false 停止队列中所有的动画
- goToEnd 是否将停止的动画 停止在当前动画的最后一个状态
