### 通过 append() 和 prepend() 方法添加若干新元素

append 和 prepend() 是在该class/id**内的**前面或者后面追加.

###  after() 和 before() 方法
after() 和 before() 方法是在该class/id 前面或者后面追加.

## class相关

### jQuery addClass() 方法

下面的例子展示如何向不同的元素添加 class 属性。当然，在添加类时，您也可以选取多个元素

### jQuery removeClass() 方法

下面的例子演示如何不同的元素中删除指定的 class 属性：

```
$("button").click(function(){
  $("h1,h2,p").removeClass("blue");
});
```

### jQuery toggleClass() **方法**

下面的例子将展示如何使用 jQuery toggleClass() 方法。该方法对被选元素进行添加/删除类的切换操作：

```
$("button").click(function(){
  $("h1,h2,p").toggleClass("blue");
});
```

## jQuery遍历

### jQuery parent() 方法

parent() 方法返回被选元素的直接父元素。

该方法只会向上一级对 DOM 树进行遍历。

下面的例子返回每个 <span> 元素的的直接父元素：

```
$(document).ready(function(){
  $("span").parent();
});
```

### jQuery parents() 方法

parents() 方法返回被选元素的所有祖先元素，它一路向上直到文档的根元素 (<html>)。

下面的例子返回所有 <span> 元素的所有祖先：

```
$(document).ready(function(){
  $("span").parents();
});
```

### jQuery parentsUntil() 方法

parentsUntil() 方法返回介于两个给定元素之间的所有祖先元素。

下面的例子返回介于 <span> 与 <div> 元素之间的所有祖先元素：

```
$(document).ready(function(){
  $("span").parentsUntil("div");
});
```

### jQuery children() 方法

children() 方法返回被选元素的所有直接子元素。

该方法只会向下一级对 DOM 树进行遍历。

下面的例子返回每个 <div> 元素的所有直接子元素：
```
$(document).ready(function(){
  $("div").children();
});
```
您也可以使用可选参数来过滤对子元素的搜索。

下面的例子返回类名为 "1" 的所有 <p> 元素，并且它们是 <div> 的直接子元素：

```
$(document).ready(function(){
  $("div").children("p.1");
});
```
### jQuery find() 方法

find() 方法返回被选元素的后代元素，一路向下直到最后一个后代。

下面的例子返回属于 <div> 后代的所有 <span> 元素：
```
$(document).ready(function(){
  $("div").find("span");
});
```
下面的例子返回 <div> 的所有后代：
```
$(document).ready(function(){
  $("div").find("*");
});
```

###  在 DOM 树中水平遍历

有许多有用的方法让我们在 DOM 树进行水平遍历：

- siblings()  siblings() 方法返回被选元素的所有同胞元素。
- next()  next() 方法返回被选元素的下一个同胞元素。
- nextAll()  nextAll() 方法返回被选元素**后**的所有跟随的同胞元素。
- nextUntil()   nextUntil() 方法返回介于两个给定参数之间的所有跟随的同胞元素。
- prev()
- prevAll()
- prevUntil()

prev(), prevAll() 以及 prevUntil() 方法的工作方式与上面的方法类似，只不过方向相反而已：它们返回的是前面的同胞元素（在 DOM 树中沿着同胞元素向后遍历，而不是向前）。

### 选择过滤

+ first() 方法返回被选元素的首个元素。

+ last() 方法返回被选元素的最后一个元素。

+ eq() 方法返回被选元素中带有指定索引号的元素。

  索引号从 0 开始，因此首个元素的索引号是 0 而不是 1。下面的例子选取第二个 <p> 元素（索引号 1）：

+ filter() 方法允许您规定一个标准。不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回。

  下面的例子返回带有类名 "intro" 的所有 <p> 元素：

  ```
  $(document).ready(function(){
    $("p").filter(".intro");
  });
  ```

+ not() 方法返回不匹配标准的所有元素。

  提示：not() 方法与 filter() 相反。

  下面的例子返回不带有类名 "intro" 的所有 <p> 元素：

