# Web端热图

## 一、热图绘制规则：

热图模式中间的热图区域显示的是，在选定的时间段和页面（而不只是热图中的当前可视区域）中，点击量在数据总量里前 1000 的元素里，有内容或有链接的元素。没有内容和链接的元素将会被过滤，以防止混淆元素的干扰，同时，您也可以通过点击热区来进行快速圈选操作。

![](../../.gitbook/assets/1-6.png)

其他绘制规则： 在当前页面的可视区域内的元素可被绘出，如果元素有一半或一半以上超出了当前可视区域，则不绘图。 元素在浏览器层面被识别为可见，即可被绘制。（比如：页面中需要鼠标点击或悬停的下拉菜单，肉眼不可见，但浏览器可见，热图可被绘出。）

## 二、元素点击率计算方式：

热图中元素的鼠标悬停提示，Dashboard 中的点击率排名的计算方式为： 元素点击率 = 元素点击量 / 当前页面PV

![](../../.gitbook/assets/2-3.png)

## 三、监控面板说明：

当前页面整体的数据概况（不随可见区域变动而变化，只随时间和页面组条件变化而刷新。）

**页面组：**

![](../../.gitbook/assets/3.png)

可将所有页面结构相似的页面，定义为一个页面组，比如产品详情页面，可以将所有产品详情页面定义为一个页面组，查看所有详情页面的热图情况。

注意事项：如果在A页面中定义了一个和A结构不符的B页面的页面组，那么B页面组则不会在该列表中显示，需要切换到B页面查看该页面组。（比如：如果在产品详情页定义了一个产品列表页的页面组，那么在当前页面中，新定义的页面组不会被展示出来。需要切换到列表页面查看。）

**点击率排名：**

当前页面中点击率前 15 的元素的排名列表， 注意事项：一个元素，至少有值（value）或链接（href）中的一项可在列表中出现。

![](../../.gitbook/assets/4-3%20%281%29.png)

## **四、绘制方式的影响范围：**

由于绘制方式的特殊性，会在不同页面结构产生以下可能发生的影响：

* 页面中的嵌套元素，在绘制时叠加，视觉上会产生热度误差。
* 页面中链接路径完全一样，热图上的元素数据也会完全一致。
* 页面动态内容, 导致画图定位不准确。（比如：轮播图，会导致被隐藏区域内的元素热图被绘制）
* 伪状态的隐藏，程序无法识别该元素为藏，绘制了热图。导致热图绘制紊乱。（比如，有交互隐藏图层，会导致被隐藏的，肉眼不可见的图层被绘制）
* 当特殊页面结构：导航条、tab在页面滚动后被隐藏，热点重绘有误。
* 用户网站body 的positon 定位有问题，会导致热图绘制问题。
* URL尾参（Query）不被区分:  如果页面内容依赖于query的话，并且页面结构不同的话，那么会产生热区绘制误差的情况。

## 五、其他具体圈选规则

可以参见 [web 圈选](https://docs.growingio.com/Features/circle/Web.html)。
