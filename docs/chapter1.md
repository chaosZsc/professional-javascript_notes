# JavaScript简介

## JavaScript简史

JavaScript诞生于1995年。当时，它的主要目的是处理一些验证操作。而今天的JavaScript已经成为一门功能全面的编程语言，能够处理复杂的计算和交互，拥有了闭包、匿名(lamda，拉姆达)函数，甚至元编程等特性。

## JavaScript实现

一个完整的JavaScript实现应该有下列三个不用的部分组成。

* 核心(`ECMAScript`)
* 文档对象模型(`DOM`)
* 浏览器对象模型(`BOM`)

### ECMAScript

由ECMA-262定义的`ECMAScript`与Web浏览器没有依赖关系。实际上，这门语言本身并不包含输入和输出定义。ECMA-262定义的只是这门语言的基础，而在此基础之上可以构建更完善的脚本语言。我们常见的Web浏览器只是`ECMAScript`实现可能的宿主环境之一。宿主环境不仅提供基本的`ECMAScript` 实现，同时也会提供该语言的扩展，以便语言与环境之间对接交互。而这些扩展——如`DOM`，则利用`ECMAScript`的核心类型和语法提供更多更具体的功能，以便实现针对环境的操作。其他宿主环境包括Node(一种服务端JavaScript平台)和Adobe Flash。

大致来说，ECMA-262规定了这门语言的下列组成部分：

* 语法
* 类型
* 语句
* 关键字
* 保留字
* 操作符
* 对象

`ECMAScript`就是对实现该标准规定的各个方面内容的语言的描述。JavaScript实现了`ECMAScript`，Adobe ActionScript同样也实现了`ECMAScript`。

ECMA-262也给出了`ECMAScript`兼容的定义。要想成为`ECMAScript`的实现，则该实现必须做到：

* 支持ECMA-262描述的所有“类型、值、对象、属性、函数以及程序句法和语义”(ECMA-262第1页)；
* 支持Unicode字符标准。

此外，兼容的实现还可以进行下列扩展：

* 添加ECMA-262没有描述的“更多类型、值、对象、属性和函数”。ECMA-262所说的这些新增特性，主要是指该标准中没有规定的新对象和对象的新属性。
* 支持ECMA-262没有定义的“程序和正则表达式语法”。(也就是说，可以修改和扩展内置的正则表达式语法。)

### 文档对象模型(`DOM`)

文档对象模型(`DOM`，Document Object Model)是针对XML但经过扩展用于HTML的应用程序编程接口(API，Application Programming Interface)。`DOM`把整个页面映射为一个多层节点结构。

通过`DOM`创建的这个表示文档的树形图，开发人员获得了控制页面内容和结构的主动权。借助`DOM`提供的API，开发人员可以轻松自如地删除、添加、替换或修改任何节点。

#### `DOM`级别

`DOM`1级由两个模块组成：`DOM`核心(DOM Core)和`DOM` HTML。其中，`DOM` 核心规定的是如何映射基于XML的文档结构，以便简化对文档中任意部分的访问和操作。`DOM` HTML模块则在`DOM`核心的基础上加以扩展，添加了针对HTML的对象和方法。

`DOM`2级引入了下列新模块，也给出了众多新类型和新接口的定义：

* `DOM`视图(DOM Views)：定义了跟踪不同文档(例如，应用CSS之前和之后的文档)视图的接口；
* `DOM`事件(DOM Events)：定义了事件和事件处理的接口；
* `DOM`样式(DOM Style)：定义了基于CSS为元素应用样式的接口；
* `DOM`遍历和范围(DOM Traversal and Range)：定义了遍历和操作文档树的接口。

`DOM`3级则进一步扩展了`DOM`，引入了以统一方式加载和保存文档的方法——在`DOM`加载和保存(DOM Load and Save)模块中定义；新增了验证文档的方法——在`DOM`验证(DOM Validation)模块中定义。`DOM`3级也对`DOM`核心进行了扩展，开始支持XML 1.0规范，涉及XML Infoset、XPath和XML Base。

### 浏览器对象模型(`BOM`)

从根本上讲，`BOM`只处理浏览器窗口和框架；但人们习惯上也把所有针对浏览器的JavaScript扩展算作`BOM`的一部分。下面就是一些这样的扩展：

* 弹出新浏览器窗口的功能；
* 移动、缩放和关闭浏览器窗口的功能；
* 提供浏览器详细信息的`navigator`对象；
* 提供浏览器所加载页面的详细信息的`location`对象；
* 提供用户显示器分辨率详细信息的`screen`对象；
* 对cookies的支持；
* 像`XMLHttpRequest`和IE的`ActiveXObject`这样的自定义对象。