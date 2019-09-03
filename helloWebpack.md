# 认识 webpack

?> webpack 是一个现代 JavaScript 应用程序的静态模块打包器(module bundler)。

当 webpack 处理应用程序时，它会递归地构建一个依赖关系图(dependency graph)，其中包含应用程序需要的每个模块，然后将所有这些模块打包成一个或多个 bundle。

**简单来说，webpack 就是一个打包工具。**


+ #### 何为模块

?> 在模块化编程中，开发者将程序分解成离散功能块(discrete chunks of functionality)，并称之为模块。

Node.js 从最一开始就支持模块化编程。然而，在 web，模块化的支持正缓慢到来。在 web 存在多种支持 JavaScript 模块化的工具，这些工具各有优势和限制。webpack 基于从这些系统获得的经验教训，并将模块的概念应用于项目中的任何文件。

下面这张图就很好的说了 webpack 的作用。

![webpack_logo](http://images.leegeing.cn/hexoImg/webpack_logo.png)