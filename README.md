记录下我看《javascript高级程序设计（第三版）》的一些笔记，也顺便学习下Git和GitHub的相关操作撒。毕竟实践出真知！

![](./docs/images/html_logo.jpg) ![](./docs/images/css_logo.jpg) ![](./docs/images/js_logo.jpg) ![](./docs/images/github_logo.jpg)

# 四logo镇楼！

## 第一章 [JavaScript简介](./docs/chapter1.md)

JavaScript 是一种专为与网页交互而设计的脚本语言，由下列三个不同的部分组成:
* `ECMAScript`，由 ECMA-262 定义，提供核心语言功能;
* 文档对象模型(`DOM`)，提供访问和操作网页内容的方法和接口;
* 浏览器对象模型(`BOM`)，提供与浏览器交互的方法和接口。

## 第二章 [在HTML中使用JavaScript](./docs/chapter2.md)

把JavaScript插入到HTML页面中要使用`<script>`元素。使用这个元素可以把JavaScript嵌入到HTML页面中，让脚本与标记混合在一起;也可以包含外部的JavaScript文件。而我们需要注意的地方有:

* 在包含外部JavaScript文件时，必须将`src`属性设置为指向相应文件的URL。而这个文件既可以是与包含它的页面位于同一个服务器上的文件，也可以是其他任何域中的文件。
* 所有`<script>`元素都会按照它们在页面中出现的先后顺序依次被解析。在不使用`defer`和`async`属性的情况下，只有在解析完前面`<script>`元素中的代码之后，才会开始解析后面`<script>`元素中的代码。
* 由于浏览器会先解析完不使用`defer`属性的`<script>`元素中的代码，然后再解析后面的内容，所以一般应该把`<script>`元素放在页面最后，即主要内容后面，`</body>`标签前面。
* 使用`defer`属性可以让脚本在文档完全呈现之后再执行。延迟脚本总是按照指定它们的顺序执行。
* 使用`async`属性可以表示当前脚本不必等待其他脚本，也不必阻塞文档呈现。不能保证异步脚本按照它们在页面中出现的顺序执行。

另外，使用`<noscript>`元素可以指定在不支持脚本的浏览器中显示的替代内容。但在启用了脚本的情况下，浏览器不会显示`<noscript>`元素中的任何内容。