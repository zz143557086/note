```
切换到frame
wd.switch_to.frame(frame_reference)
其中，frame_reference可以是：
frame元素的Id属性
frame元素的name属性
frame对应的WebElement对象
切回原来的主html
wd.switch_to.default_content()
```

```
切换新窗口
wd.switch_to.window(handle)
参数handle：操作窗口的句柄
WebDriver对象有window_handles属性，这是一个列表对象， 里面包括了当前浏览器里面所有的窗口句柄。所谓句柄，可以看成是对应网页窗口的一个ID，那么我们就可以通过类似下面的代码切换到对应的网页窗口：
切回原来的窗口

for handle in wd.windao_handles:
	# 依次切换窗口
	wd.switch_to.window(handle)
	# 根据窗口的标题栏字符判断是否是我们要操作的那个窗口
	if 'XXX' in wd.title:
		# 如果是，那么这时候WebDriver对象就是对应的该窗口，跳出循环
		break
# mainWindow变量保存当前窗口的句柄
mainWindow = wd.current_window_handle
...
# 通过前面保存的老窗口的句柄，切换到老窗口
wd.switch_to.window(mainWindow)
```

