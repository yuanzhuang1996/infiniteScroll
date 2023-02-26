
# 这是一个基于 JavaScript 的简单无限滚动插件。它可以用于在页面滚动时加载更多内容，实现无限滚动效果。

## 使用方法
```
1. 引入插件
2. 将 infinite-scroll.js 文件引入到您的 HTML 中：
```

如果您使用模块化开发，可以使用 ES6 的 import 语法：

```
import InfiniteScroll from "./infinite-scroll.js";
const container = document.querySelector("infinite-scroll");
const items = Array.from(container.querySelectorAll(".infinite-scroll-item"));
const infiniteScroll = new InfiniteScroll({
  container: container,
  items: items,
  limit: 10,
  callback: (newItems) => {
    for (let item of newItems) {
      container.appendChild(item);
    }
  },
});
```



//例子一
|名称|描述|类型|
|:-|:-:|-:|
|container|包含滚动内容的容器元素|element|
|items|需要滚动的元素列表|element|
|limit|每次加载的元素数量|number|
|callback|在加载新元素后执行的回调函数|function|

```
销毁实例
当您不再需要滚动功能时，可以销毁实例：
infiniteScroll.destroy();
```
示例
以下是一个使用无限滚动插件的示例：

```
<div class="infinite-scroll">
  <div class="infinite-scroll-item">Item 1</div>
  <div class="infinite-scroll-item">Item 2</div>
  <div class="infinite-scroll-item">Item 3</div>
  <!-- ... -->
</div>
<script src="infinite-scroll.js"></script>
<script>
const container = document.querySelector(".infinite-scroll");
const items = Array.from(container.querySelectorAll(".infinite-scroll-item"));

const infiniteScroll = new InfiniteScroll({
  container: container,
  items: items,
  limit: 10,
  callback: (newItems) => {
    for (let item of newItems) {
      container.appendChild(item);
    }
  },
});
</script>
```

### 注意事项
- 插件只能在浏览器端使用，不能在 Node.js 环境下使用。
- 插件只能用于静态元素，不能用于动态元素（例如 Vue、React 等框架中的组件）。
- 您可能需要根据自己的需求进行修改，例如修改加载新元素的方式、修改滚动容器的高度等。