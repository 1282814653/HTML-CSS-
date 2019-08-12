# html 与 css 的总结

- html 是超文本标记语言 是负责页面的布局的
- css 是层叠样式表 是负责 页面的结构的
- html + css 组合使用完成页面的布局设置
- 标签有很多属性 但常用的都差不多 除了特别少见的结构样式(多看文档查文档)
- 要发散性的学习 html 与 css 组合应用太强
- 在 html 基础中主要掌握的就是标签的合理使用
- html 中知道常用的标签要知道那些是 块元素,那些是 行内块元素 ,那些是 行内块元素 知道怎么使用块元素与行内元素,行内块元素.它们之间都是可以互相可以转换的
  - 块元素是 独占一行 会换行 可以设置宽高 margin padding 参数都可以设置 display:block
  - 行内元素是 可以并列排序不会换行 不可以设置宽高 margin padding 的 top/bottom 参数不可以设 display:inline
  - 行内块是 不会换行(综合里快与行内的优点) 但是可以有宽高 margin padding 参数都可以设定 display: inline-block
- css 基础中主要掌握的是就是 float(浮动)产生的变化及浮动产生的后果和怎么解决.position 定位 中要知道定位的使用方式和几种定位的方法.
- position 可以设定相对定位 relative 相对于自己
  绝对定位 absolute 相对于最近的 relative
  固定定位 fixed 相对于当前页面
  粘性定位 sticky 设置参数达到要求就会触发粘性定位
- 选择器的使用 id 属性 和 class 还有 交集 并集 \*通配 和 父子 等一系列选择器
- :hover 要熟悉应用 hover 效果 搞清楚层次理论
