# jq 节点的操作

## 创建元素

- var node = \$('#box').html('<a>这是 a 标签</a>');

## 添加元素

1.  append()

- 在被选元素内部的最后一个子元素（或内容）后面插入内容（存在或者创建出来的元素都可以）
- 如果是页面中存在的元素，那么调用 append()后，会把这个元素放到 相应的目标元素里面去；但是，原来的这个元素，就不存在了。
  如果是给多个目标追加元素，那么方法的内部会复制多份这个元素，然后追加到多个目标里面去。

2. appendTo()

- 把\$(selector)追加到 node 中去
- \$(selector).appendTo(node);

3. prepend()

- 在元素的第一个子元素前面追加内容或节点
- \$(selector).prepend(node);

4.  after()

- 在被选元素之后，作为兄弟元素插入内容或节点
- \$(selector).after(node);

5.  before()

- 在被选元素之前，作为兄弟元素插入内容或节点
- \$(selector).before(node);

## 清除元素

- \$(selector).empty();
- \$(selector).html(“”);
- \$(selector).remove(); //会把对象也干掉

## 赋值元素

- \$(selector).clone();//深复制 标签里面的内容也会被复制
