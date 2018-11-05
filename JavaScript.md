# JavaScript 

## jQuery

### 加载方法

首先在页面顶端增加一行`script`元素，然后写上结束符。浏览器会运行`script` 里所有的Javascript，包括jQuery。在你的`script`里，添加这个方法:`$(document).ready(function() {`到你的`script`，接下来用`});`结束这个方法接下来我们来学习如何写`方法`，`方法`里面的代码会被浏览器加载。在没有`document ready function`以前，你的代码会在HTML没有渲染完成就执行，这样会产生bug。

<script>
  $(document).ready(function(){});
</script>

### How to target

> 现在我们已经知道 `document ready function`的用法了.
>
> 现在让我们开始写第一个jQuery语句，所有jQuery方法都是由`$`开始的，通常称作为 `美元符号`，或者简称为`bling`。
>
> jQuery通过`选择器`来选择一个元素的，然后操作元素做些改变。
>
> 举个例子，要让所有的`按钮`做弹回效果，只要把这段代码写在`document ready function`里面就可以了。
>
> ```
> $("button").addClass("animated bounce");
> ```
>
> 我们已经在后台为你引入了jQuery库和Animate.css库，这样你就可以在编辑器里直接可以使用这两个库，进而通过jQuery给`button`元素添加`bounce`回弹动画效果。

<script>
  $(document).ready(function() {
    $("button").addClass("animated bounce");
  });
</script>

> #### Target Elements by Class Using jQuery
>
> 你看到我们是怎么给所有的`按钮`做弹回效果了吗？我们用 `$("button")`来选中按钮，然后用`.addClass("animated bounce")`给按钮加CSS class。
>
> 你只需要用jQuery的`.addClass()`方法，就可以给元素加class了。
>
> 首先，我们来使用`$(".well")`来获取所有class为`well`的`div`元素。
>
> 仔细想想为什么需要在`well`前面添加`.`
>
> 然后使用jQuery的`.addClass()`方法添加2个class：`animated`、`shake`。
>
> 例如，你可以将下面的代码写在`document ready function`里：
>
> ```
> $(".text-primary").addClass("animated shake");
> ```
>
> 上面的代码给所有class为`text-primary` 的元素添加shake class.

<script>
  $(document).ready(function() {
    $("button").addClass("animated bounce");
    $(".well").addClass("animated shake");
  });
</script>

> 现在你已经了解了3种选择器：元素选择器：`$("button")`、class选择器：`$(".btn")`、id选择器：`$("#target1")`。
>
> 尽管用`.addClass()`这种方式就可以加不同的class，不过还是让我们尝试用不同的方式给元素添加class吧。
>
> 用上面介绍的jQuery选择器和`addClass()`方法：
>
> 给所有type为`button`的元素添加`animated` class。
>
> 给所有class为`.btn`的按钮添加`shake` class。
>
> 给所有id为`#target1`的按钮添加`btn-primary` class。



###  CSS

> #### Change the CSS of an Element Using jQuery
>
> 我们可以通过jQuery来改变HTML元素的CSS样式。
>
> jQuery有一个叫做`.css()`的方法能让你改变元素的CSS样式。
>
> 我们是这样来把颜色改变成蓝色的:
>
> ```
> $("#target1").css("color", "blue");
> ```
>
> 这跟通常的CSS语法有点不同，这里CSS的属性和值是在引号内的，并且用逗号分开。

### Disable

> 你还可以用jQuery改变除了CSS以外的属性。比如，你可以让按钮变不可选。
>
> 当你把按钮设置成不可选以后，这会让按钮变灰并且不能点击。
>
> jQuery有一个`.prop()`的方法让你来调整元素的属性.
>
> 我们是这样来让按钮不可选的:
>
> ```
> $("button").prop("disabled", true);
> $("button").prop("disabled", true);
> ```
>
> 来尝试让 `target1` 按钮不可选.

### CHANGE Text Inside an Element

> jQuery不仅可以改变元素开始标记和结束标记间的文本，甚至可以改变元素标记本身。
>
> jQuery的`.html()`方法可以添加HTML标签和文字到元素，而元素之前的内容都会被方法的内容所替换掉。
>
> 我们是通过`em`[emphasize]标签来重写和强调标题文本的：
>
> ```
> $("h3").html("<em>jQuery Playground</em>");
> ```
>
> jQuery 还有一个类似的方法叫`.text()`，它只能改变文本但不能修改标记。换句话说，这个方法只会把传进来的任何东西(包括标记)当成文本来显示。
>
> 任务：强调id为`target4`按钮里的文本。

### Remove an Element Using jQuery

> 现在让我们用jQuery来移除页面上的HTML元素吧.
>
> jQuery 有一个`.remove()` 的方法可以移除HTML元素
>
> 试着使用`.remove()`方法来移除页面上的`target4`元素吧.

### Use appendTo to Move Elements with jQuery

> 现在让我们尝试把元素从一个`div`里移到另外一个`div`里。
>
> jQuery有一个`appendTo()`方法可以把选中的元素加到其他元素中。
>
> 比如，你想让`target4`从我们的从`right-well`移到`left-well`，我们可以这样使用:
>
> ```
> $("#target4").appendTo("#left-well");
> ```
>
> 来试着把`target2`元素从`left-well`移到`right-well`中。

### Clone an Element Using jQuery

> 除了移动元素，你还可以拷贝元素。简单理解：移动元素就是剪切，拷贝元素就是复制。
>
> jQuery的`clone()`方法可以拷贝元素。
>
> 比如，如果我想把`target2`从`left-well`拷贝到`right-well`，我们可以这样写:
>
> ```
> $("#target2").clone().appendTo("#right-well");
> ```
>
> 你有没有发现两个jQuery方法合在一起使用了？这就叫方法链`function chaining`，使用起来很方便。
>
> 复制`target5`元素追加到`left-well`

### Target the Parent of an Element Using jQuery

> 每个HTML元素根据继承属性都有父`parent`元素。
>
> 举个例子，`h3` 元素的父元素是 `<div class="container-fluid">`，`<div class="container-fluid">`的父元素是 `body`。
>
> jQuery有一个方法叫`parent()`，它允许你访问指定元素的父元素。
>
> 举个例子：让`left-well` 元素的父元素`parent()`的背景色变成蓝色。
>
> ```
> $("#left-well").parent().css("background-color", "blue")
> ```
>
> 试试让`#target1`元素的父元素的背景色变成红色。

### Target the Children of an Element Using jQuery

> 每个人都继承了自己的父母的一些属性，譬如：DNA、相貌、血型、体型等等，HTML也不例外。
>
> 许多HTML元素都有`children`(子元素)，每个子元素都从父元素那里继承了一些属性。
>
> 举个例子，每个HTML元素都是 `body` 的子元素， 你的 "jQuery Playground" `h3` 元素是 `<div class="container-fluid">` 的子元素。
>
> jQuery有一个方法叫`children()`，它允许你访问指定元素的子元素。
>
> 举个例子：让`left-well` 元素的子元素`children()`的文本颜色变成蓝色。
>
> ```
> $("#left-well").children().css("color", "blue")
> ```

### Target a Specific Child of an Element Using jQuery

> 你已经看到了当用jQuery选择器通过id属性来选取元素的时候是多么方便，但是你不能总是写这么整齐的id。
>
> 幸运的是，jQuery有一些另外的技巧可以达到同样的效果。
>
> jQuery 用CSS选择器来选取元素，`target:nth-child(n)` CSS选择器允许你按照索引顺序(从1开始)选择目标元素的所有子元素。
>
> 示例：你可以给目标元素的第三个子元素添加bounce class。
>
> ```
> $(".target:nth-child(3)").addClass("animated bounce");
> ```
>
> 任务：确保给目标元素的第二个子元素添加animated和bounce class，你可以通过`target`class来选获得目标元素。

### Target Even Numbered Elements Using jQuery

> 示例：获取class为`target`且索引为奇数的所有元素，并给他们添加class。
>
> ```
> $(".target:odd").addClass("animated shake");
> ```
>
> 记住，jQuery里的索引是从0开始的，也就是说：`:odd` 选择第2、4、6个元素，因为target#2(索引为1)，target#4(索引为3)，target6(索引为5。
>
> 任务：获取class为`target`且索引为偶数的所有元素，也就是target#1(索引为0)，target#3(索引为2)，target5(索引为4)，并给它们添加class `animated` 和 `shake`。

### Use jQuery to Modify the Entire Page

> 我们已经玩了这么久的jQuery游乐场，是时候结束这一节了。
>
> 我们让整个body都有淡出效果(fadeOut)： `$("body").addClass("animated fadeOut");`
>
> 让我们做一些更为激动人心的事情，给body添加class `animated` 和`hinge` 。

## JavaScript

### POP PUSH SHITF UNSHIFT

myObj.val || myObj[val]

myObj.hasOwnProperty("val");



> var ourMusic = [
>   {
> ​    "artist": "Daft Punk",
> ​    "title": "Homework",
> ​    "release_year": 1997,
> ​    "formats": [ 
> ​      "CD", 
> ​      "Cassette", 
> ​      "LP" ],
> ​    "gold": true
>   }
> ];

这是一个对象数组

Math.random();0~1随机小数

1. 用 `Math.floor()` 向下取整 获得它最近的整数。

### 正则表达式

------

`Regular expressions` 正则表达式被用来根据某种匹配模式来寻找`strings`中的某些单词。

举例：如果我们想要找到字符串`The dog chased the cat`中单词 `the`，我们可以使用下面的正则表达式: `/the/gi`

我们可以把这个正则表达式分成几段：

`/` 是这个正则表达式的头部

`the` 是我们想要匹配的模式

`/` 是这个正则表达式的尾部

`g` 代表着 `global`(全局)，意味着返回所有的匹配而不仅仅是第一个。

`i` 代表着忽略大小写，意思是当我们寻找匹配的字符串的时候忽略掉字母的大小写。

```
var expression = /and/gi;  // 此代码找到了在全局中找到了全部两个and
```

### \d+

我们可以在正则表达式中使用特殊选择器来选取特殊类型的值。

特殊选择器中的一种就是数字选择器`\d`，意思是被用来获取一个字符串的数字。

在JavaScript中, 数字选择器类似于: `/\d/g`。

在选择器后面添加一个加号标记(`+`)，例如：`/\d+/g`，它允许这个正则表达式匹配一个或更多数字。

尾部的`g`是'global'的简写，意思是允许这个正则表达式 找到所有的匹配而不是仅仅找到第一个匹配。

### \s | \S

我们也可以使用正则表达式选择器 `\s` 来选择一个字符串中的空白。

空白字符有 `" "` (空格符)、`\r` (回车符)、`\n` (换行符)、`\t` (制表符) 和 `\f` (换页符)。

空白正则表达式类似于：

```
/\s+/g
```

\S

------

你可以用正则表达式选择器的大写版本 来转化任何匹配。

举个例子：`\s` 匹配任何空白字符，`\S` 匹配任何非空白字符。

用 `/\S/g` 来匹配字符串`testString`中的所有非空白字符。

\S 49 \S+ 9

### 构造函数

除了上一种方法外，我们还可以使用**构造函数**来创建对象。

**构造函数** 通常使用大写字母开头，以便把自己和其他普通函数区别开。

下面便是一个 **构造函数** 了：

> var Car = function() {
>   this.wheels = 4;
>   this.engines = 1;
>   this.seats = 1;
> };

在 **构造函数** 中， `this` 指向被此 **构造函数** 创建出来的 **对象** 。所以，当我们在 **构造函数** 中写：

```
  this.wheels = 4;
```

这时，它创建出来的新**对象**将带有 `wheels` 属性，并且赋值为 `4`.

你可以认为 **构造函数** 描述了它所创建出来的**对象**。

让你的 `MotorBike` **构造函数** 描述一个具有 `wheels`, `engines` 和 `seats` 属性的 **对象** ，并且为这些属性设置值。

#### 调用

现在，我们把上一节课我们写的 **构造函数** 在这里用起来！

使用构造函数时，我们通过在它前面使用 `new` **关键字** 来对它进行调用，如下：

```
var myCar = new Car();
```

`myCar` 现在成为了 `Car` 的一个 **实例**（instance），它被 **构造函数** 描述成下面的样子：

> {
>   wheels: 4,
>   engines: 1,
>   seats: 1
> }

记住：要使用 `new` **关键字** 去调用构造函数。因为只有这样，Javascript才知道这是要去构造一个新 **对象** ，并且把构造函数中的 `this` 指向这个新对象。

现在，当 `myCar` （即 `Car` 的一个 **实例** ）创建后，他可以像普通对象一样被使用，包括创建、访问、修改它的属性等，就像我们使用其他对象一样。如下：

```
myCar.turboType = "twin";
```

我们的 `myCar` 变量现在有了一个 `turboType` 属性了，且值为 `"twin"` 。

在编辑器中，使用 `Car` 这个构造函数去创建一个新的 **实例** ，并且把这个实例赋值给 `myCar` 。

然后给 `myCar` 创建一个 `nickname` 属性，且属性值为一个字符串

#### 变量对象

我们之前写的 `构造函数` 很好，但是我们不想总是创建相同的对象，怎么办呢？

为了解决这个问题，我们要向 `构造函数` 中添加 `参数` 。像下面这样：

> var Car = function(wheels, seats, engines) {
>   this.wheels = wheels;
>   this.seats = seats;
>   this.engines = engines;
> };

现在，我们可以在调用 `构造函数` 时传入一组 `参数` 了。

```
var myCar = new Car(6, 3, 1);
```

这段代码将会使用这一组 `参数` 来创建出下面的对象：

> {
>   wheels: 6,
>   seats: 3,
>   engines: 1
> }

现在该你试试了！改动 `Car` 的 `构造函数` ，使它能够通过使用 `参数` 来为 `wheels` 、 `seats` 、 `engines` 属性进行赋值。

然后调用你刚刚改写过的 `构造函数` ，并传入三个 `参数` ，我们就能看到创建的新对象赋值给了 `myCar` 。

```var Car = function(wheels,seats,engines) {
var Car = function(wheels,seats,engines) {  
  //Change this constructor
  this.wheels = wheels;
  this.seats = seats;
  this.engines = engines;
};

//Try it out here
var myCar = new Car(3,1,2);
```

### 属性与方法, 私有属性,私有方法

对象拥有自己的特征，称为 `属性`，对象还有自己的函数，称为 `方法` 。

在前面的课程（构造函数）中，我们使用了 `this` 指向当前（将要被创建的）对象中的 `公有属性` 。

我们也可以创建 `私有属性` 和 `私有方法` ，它们两个在对象外部是不可访问的。

为了完成这个任务，我们在 `构造函数` 中，使用我们熟悉的 `var` 关键字去创建变量，来替代我们使用 `this` 创建 `属性` 。

比如，我们想记录我们的car行驶的 `speed` ，但是我们希望外面的代码对 `speed` 的修改只能是加速或减速（而不是变成字符串、直接赋值成某个速度等其他操作），那么如何达到这类操作的目的呢？

编辑器中的 `构造函数` 展示了如何实现这种控制模式。

该你自己试试了！修改 `Bike` 的 `构造函数` ，使它有一个名为 `gear` 的 `私有属性` ，还有两个公有方法，叫做 `getGear` 和 `setGear` ，这两个方法用来获得和设置 `gear` 的值。

```var Car = function() {
var Car = function() {
 // this is a private variable
  var speed = 10;

  // these are public methods
  this.accelerate = function(change) {
    speed += change;
  };

  this.decelerate = function() {
    speed -= 5;
  };

  this.getSpeed = function() {
    return speed;
  };
};

var Bike = function() {
  // 只能在这一行下面写代码
   var gear = 0;
  this.getGear = function(){
    return gear;
  }
  this.setGear = function(numbers){
    gear = numbers;
  }
};
```

### MAP 迭代数组

`map` 方法可以方便的迭代数组，例子：

> var timesFour = oldArray.map(function(val){
>   return val * 4;
> });

`map` 方法会迭代数组中的每一个元素，并根据回调函数来处理每一个元素，最后返回一个新数组。注意，这个方法不会改变原始数组。

在我们的例子中，回调函数只有一个参数，即数组中元素的值 (`val` 参数) ，但其实，你的回调函数也可以支持多个参数，譬如：元素的索引`index`、原始数组`arr`。

使用 `map` 方法来为 `oldArray` 中的每一项增加3，并且在 `newArray` 中保存它们。 `oldArray` 不应该被改变。

### reduce 方法迭代数组

数组方法 `reduce` 用来迭代一个数组，并且把它累积到一个值中。

使用 `reduce` 方法时，你要传入一个回调函数，这个回调函数的参数是一个 **累加器** （比如例子中的 `previousVal`) 和当前值 (`currentVal`）。

`reduce` 方法有一个可选的第二参数，它可以被用来设置累加器的初始值。如果没有在这定义初始值，那么初始值将变成数组中的第一项，而 `currentVal` 将从数组的第二项开始。

下面的例子使用了 `reduce` 来让数组中的所有值相减：

> var singleVal = array.reduce(function(previousVal, currentVal) {
>   return previousVal - currentVal;
> }, 0);

使用 `reduce` 方法来让 `array` 中的所有值相加，并且把结果赋值给 `singleVal` 。

### Filter 方法迭代数组

`filter` 方法用来迭代一个数组，并且按给出的条件过滤出符合的元素。

`filter` 方法传入一个回调函数，这个回调函数会携带一个参数，参数为当前迭代的项（我们叫它 `val` ）。

回调函数返回 `true` 的项会保留在数组中，返回 `false` 的项会被过滤出数组。

下面的代码示例展示了使用 `filter` 来移除数组中值等于5的项：

**注意：** 我们忽略了第二参数和第三参数，因为例子中我们只需要第一参数就够了。

> array = array.filter(function(val) {
>   return val !== 5;
> });

使用 `filter` 来创建一个新数组，新数组的值是 `oldArray` 中值小于6的元素。不许改变原数组 `oldArray` 。

[Filter](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

### sort 方法排序

使用 `sort` 方法，你可以很容易的按字母顺序或数字顺序对数组中的元素进行排序。

与我们之前用的数组方法仅仅返回一个新数组不同， `sort` 方法将改变原数组，返回被排序后的数组。

`sort` 可以把比较函数作为参数传入。比较函数有返回值，当 `a` 小于 `b`，返回一个负数；当 `a` 大于 `b` ，返回一个正数；相等时返回0。

如果没有传入比较函数，它将把值全部转成字符串，并按照字母顺序进行排序。

下面的例子将展示 `sort` 的使用，传入的比较函数把元素按照从小到大的顺序进行排列：

> var array = [1, 12, 21, 2];
> array.sort(function(a, b) {
>   return a - b;
> });

使用 `sort` 按照从大到小的顺序排序 `array` 。

### Reverse Arrays with reverse

------

你可以使用 `reverse` 方法来翻转数组。

> var myArray = [1, 2, 3];
> myArray.reverse();

*结果myArray 变成了 [3, 2, 1]*

使用 `reverse` 来翻转 `array` 数组。并赋值给 `newArray`.

### Concat方法

`concat` 方法可以用来把两个数组的内容合并到一个数组中。

`concat` 方法的参数应该是一个数组。参数中的数组会拼接在原数组的后面，并作为一个新数组返回。

下面是一个拼接数组的例子，用`concat` 把 `otherArray` 拼接在 `oldArray` 的后面：

```
newArray = oldArray.concat(otherArray);
```

使用 `.concat()` 将 `concatMe` 拼接到 `oldArray`后面，并且赋值给 `newArray`。

### Split Strings with split

------

你可以使用 `split` 方法按指定分隔符将字符串分割为数组。

你要给 `split` 方法传递一个参数，这个参数将会作为一个分隔符。

下面的例子展示了 `split` 方法的使用，按照 `s` 字母进行分割：

```
var array = string.split('s');
```

使用 `split` 方法来把字符串 `string` 分割为数组 `array`。

###  Join Strings with join

-----

我们还可以使用 `join` 方法来把数组转换成字符串，里面的每一个元素可以用你指定的连接符来连接起来，这个连接符就是你要传入的参数。

下面展示了使用 `join` 来将数组中的每一项放入字符串，并用 `and `进行连接：

> var veggies = ["Celery", "Radish", "Carrot", "Potato"];
> var salad = veggies.join(" and ");
> console.log(salad); // "Celery and Radish and Carrot and Potato" 

使用 `join` 方法，连接符为`' '`把数组 `joinMe` 转化成字符串 `joinedString`.





filiter 还不是很会用