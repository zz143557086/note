```
document.createElement('tagName') //动态创建元素节点
node.appendChild(child) // 将一个节点添加到指定父节点的子节点列表末尾
node.insertBefore(child,指定元素) //将一个节点添加到指定元素前面
document.write(内容) //可以创建标签 在文档流执行后 动态会导致页面重绘
innerHTML //效率最高
```

```
node.removeChild(child) //从node中删除一个子节点，返回删除的节点
```

```
node.cloneNode() // 拷贝一份副本克隆节点 参数为空或者false为浅复制只复制本身不复制子节点 参数为true复制所有内容
```

