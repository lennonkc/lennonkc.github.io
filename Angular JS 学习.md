## Angular JS 学习

### AngularJS是JavaScript框架

> AngularJS 是一个 JavaScript 框架。它是一个以 JavaScript 编写的库。
>
> AngularJS 是以一个 JavaScript 文件形式发布的，可通过 script 标签添加到网页中：
>
> <script src="https://cdn.staticfile.org/angular.js/1.4.6/angular.min.js"></script>

AngularJS 通过 **ng-directives** 扩展了 HTML。

**ng-app** 指令定义一个 AngularJS 应用程序。

**ng-model** 指令把元素值（比如输入域的值）绑定到应用程序。

**ng-bind** 指令把应用程序数据绑定到 HTML 视图。

当网页加载完毕，AngularJS 自动开启。

**ng-app** 指令告诉 AngularJS，<div> 元素是 AngularJS **应用程序** 的"所有者"。

**ng-model** 指令把输入域的值绑定到应用程序变量 **name**。

**ng-bind** 指令把应用程序变量 name 绑定到某个段落的 innerHTML。

### 什么是 AngularJS？

AngularJS 使得开发现代的单一页面应用程序（SPAs：Single Page Applications）变得更加容易。

- AngularJS 把应用程序数据绑定到 HTML 元素。
- AngularJS 可以克隆和重复 HTML 元素。
- AngularJS 可以隐藏和显示 HTML 元素。
- AngularJS 可以在 HTML 元素"背后"添加代码。
- AngularJS 支持输入验证。

### AngularJS 表达式

AngularJS 表达式写在双大括号内：**{{ expression }}**。

AngularJS 表达式把数据绑定到 HTML，这与 **ng-bind** 指令有异曲同工之妙。

AngularJS 将在表达式书写的位置"输出"数据。

**AngularJS 表达式** 很像 **JavaScript 表达式**：它们可以包含文字、运算符和变量。

实例 {{ 5 + 5 }} 或 {{ firstName + " " + lastName }}

### AngularJS 应用

AngularJS **模块（Module）** 定义了 AngularJS 应用。

AngularJS **控制器（Controller）** 用于控制 AngularJS 应用。

**ng-app**指令指明了应用, **ng-controller** 指明了控制器。

```html
<div ng-app="myApp" ng-controller="myCtrl">
 
名: <input type="text" ng-model="firstName"><br>
姓: <input type="text" ng-model="lastName"><br>
<br>
姓名: {{firstName + " " + lastName}}
 
</div>
 
<script>
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope) {
    $scope.firstName= "John";
    $scope.lastName= "Doe";
});
</script>

```

```html
ng-init初始化数据
<div ng-app="" ng-init="quantity=1;cost=5">
 
<p>总价： <span ng-bind="quantity * cost"></span></p>
 
</div>
	使用 ng-init 不是很常见。您将在控制器一章中学习到一个更好的初始化数据的方式。
```



<script>
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope) {
    $scope.firstName= "John";
    $scope.lastName= "Doe";
});
</script>
### AngularJS  数据类型

AngularJS 对象就像 JavaScript 对象：

```html
<div ng-app="" ng-init="person={firstName:'John',lastName:'Doe'}">
 
<p>姓为 {{ person.lastName }}</p>
 
</div>
```

#### AngularJS 数组

AngularJS 数组就像 JavaScript 数组：

``` html
<div ng-app="" ng-init="points=[1,15,19,2,40]">
 
<p>第三个值为 {{ points[2] }}</p>
 
</div>
```

### 概括

AngularJS 表达式 与 JavaScript 表达式

类似于 JavaScript 表达式，AngularJS 表达式可以包含字母，操作符，变量。

与 JavaScript 表达式不同，AngularJS 表达式可以写在 HTML 中。

与 JavaScript 表达式不同，AngularJS 表达式不支持条件判断，循环及异常。

与 JavaScript 表达式不同，AngularJS 表达式支持过滤器。

### ng 指令

**ng-repeat** 指令会重复一个 HTML 元素：

```html
<div ng-app="" ng-init="names=['Jani','Hege','Kai']">
  <p>使用 ng-repeat 来循环数组</p>
  <ul>
    <li ng-repeat="x in names">
      {{ x }}
    </li>
  </ul>
</div>
```

**ng-repeat** 指令用在一个对象数组上：

```html
<div ng-app="" ng-init="names=[
{name:'Jani',country:'Norway'},
{name:'Hege',country:'Sweden'},
{name:'Kai',country:'Denmark'}]">
 
<p>循环对象：</p>
<ul>
  <li ng-repeat="x    in names">
    {{ x.name + ', ' + x.country }}
  </li>
</ul>
 
</div>
```

+ ng-app

  **ng-app** 指令定义了 AngularJS 应用程序的 **根元素**。

  **ng-app** 指令在网页加载完毕时会**自动引导**（自动初始化）应用程序。

  稍后您将学习到 **ng-app** 如何通过一个值（比如 ng-app="myModule"）连接到代码模块。

+ ng-init

  **ng-init** 指令为 AngularJS 应用程序定义了 **初始值**。

  通常情况下，不使用 ng-init。您将使用一个控制器或模块来代替它。

  稍后您将学习更多有关控制器和模块的知识。

+ ng-model

  **ng-model** 指令 **绑定 HTML 元素** 到应用程序数据。

  **ng-model** 指令也可以：

  - 为应用程序数据提供类型验证（number、email、required）。
  - 为应用程序数据提供状态（invalid、dirty、touched、error）。
  - 为 HTML 元素提供 CSS 类。
  - 绑定 HTML 元素到 HTML 表单。

+ ng-repeat

  **ng-repeat** 指令对于集合中（数组中）的每个项会 **克隆一次 HTML 元素**

+ 创建自定义的指令

  **app.directive**

```html
<body ng-app="myApp">

<runoob-directive></runoob-directive>

<script>
var app = angular.module("myApp", []);
app.directive("runoobDirective", function() {
    return {
        template : "<h1>自定义指令!</h1>"
    };
});
</script>

</body>
```

调用方式

```html
<runoob-directive></runoob-directive>
<div runoob-directive></div>
<div class="runoob-directive"></div>
<!-- directive: runoob-directive -->
```

限制调用的方式

```html
var app = angular.module("myApp", []);
app.directive("runoobDirective", function() {
    return {
        restrict : "A",
        template : "<h1>自定义指令!</h1>"
    };
});
```

> **restrict** 值可以是以下几种:
>
> - `E` 作为元素名使用
> - `A` 作为属性使用
> - `C` 作为类名使用
> - `M` 作为注释使用
>
> **restrict** 默认值为 `EA`, 即可以通过元素名和属性名来调用指令。