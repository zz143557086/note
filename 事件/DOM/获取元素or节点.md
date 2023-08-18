```
getElementById() // 返回id元素 没有返回null
```

```
element = getElementByTagName() // 返回某类的元素集合 以伪数组形式 动态 没有元素返回空的伪数组
element.getElementByTagName() 获取子元素集合
```

```
getElementByClassName() // 返回类元素集合 没有返回null
```

```
querySelector() // 返回指定选择器的第一个元素对象
```

```
querySelectorAll() // 返回指定选择器的所有元素对象集合
```

```
document.body //获取body元素
```

```
document.documentElement //获取html元素
```

```
节点层次关系来获取元素
节点包括nodeType节点类型 nodeName节点名 nodeValue节点值
元素节点类型 1  属性节点类型 2  文本节点类型 3 换行为改节点
element.parentNode 元素父节点  //离元素最近的父级节点找不到父节点返回null
element.childNodes //获取所有子节点
element.children // 获取所有元素子节点
```

```
element.firstChild // 获取第一个子节点
element.lastchild //最后一个子节点
element.firstElementChild  //第一个子元素节点
element.lastElementChild //最后一个子元素节点 找不到啊返回null
```

```
element.nextSibling //返回当前元素下一个兄弟节点 找不到返回null
element.previousSibling // 返回当前元素上一个兄弟节点 找不到返回null
element.nextElementSibling //返回当前元素下一个兄弟元素节点 找不到返回null
element.previousElementSibling // 返回当前元素上一个兄弟元素节点 找不到返回null
```

