```
相对定位：该元素相对于自己原有位置，偏移一定距离。相对的是自己。
绝对定位：该元素相对于其父元素，偏移一定距离。相对的是父元素，重点是这个父元素也需要是设置了position属性。从最近的父元素开始找，直到找到body位置为止。
固定定位:fixed 以浏览器的可视窗口为参照点移动元素。
跟父元素没有任何关系   不随滚动条滚动 固定定位不在占有原先的位置。
```

```
padding的区域默认透明，加有背景颜色，就显示背景颜色。css2.1前提下，背景颜色一定和内容区域相同。即，background-color将填充所有boder以内的区域。
border 就是边框。边框有三要素：粗细、线型、颜色 
border-width:2px;    → 边框宽度
border-style:solid;     → 线型
border-color:red;      → 颜色

transform:translate(-50%,-50%);居中
opacity:.5; 百分之五半透明
z-index:999; 挺高层级
cursor:move;鼠标变为十字的形状
overflow:hidden;溢出隐藏 清除浮动 解决外边距塌陷
overflow:auto;溢出添加滚动条

padding内边距是边框和内容之间的距离
margin外边距是标签和标签之间的距离
```

