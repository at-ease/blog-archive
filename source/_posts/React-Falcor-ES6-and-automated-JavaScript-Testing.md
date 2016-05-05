title: React Falcor ES6 and automated JavaScript Testing 
date: 2016-04-28 10:09:34
desc: 基于 React、Falcor、ES6 和自动化测试的前端技术栈实践。
from: http://engineering.widen.com/blog/future-of-the-web-react-falcor/
---

本文是对新技术的一个尝试，向各位演示构建用户界面、服务器和数据接口的新方式，换句话说，这里会同时涉及前后端的技术，最终的完整代码请查看[ GitHub 仓库](https://github.com/Widen/fullstack-react)。Widen（作者所在的公司）的传统技术栈包含了服务端的 Java 、前端的 AngularJS、处理 REST API 的 Jersey 以及其他周边库，比如 jQuery、underscore、lodash 等。为了向各位演示新技术，我设计了一些基本示例，这些示例主要遵循了以下几点：

- 技术要新颖。抛弃上述提及的现有技术栈，完全使用一套新的技术栈，从新的角度重新审视前后端开发并驱动自身的技术成长
- 学习曲线要平缓。AngularJS 1.x 的学习曲线已经够陡峭了，我发现 AngularJS 2.x 好像有过之而无不及。我非常希望避免过多的模板代码，在不影响可扩展性的同时提高应用程序的启动和运行速度。此外，实现前端开发的模块化也是目标之一。REST API 越来越难以维护和改进，前端开发者必须和后端工程师合作协议抛出一系列 API 才能正确地将 Model 数据映射到前端页面。当 UI 发生变化时，REST API 往往也需要变化，所以我们迫切需要一种新的方案
- 运行要高效。传统的 REST API 有一些痼疾，比如不必要的请求开销、过多的请求次数以及不必要的响应开销。我很少关心前端的渲染性能，因为 React 和 AugularJS 都在内部进行了很好的优化
- 代码要优雅。我一直在寻找某些方法或工具让代码变得优雅起来，便于阅读和理解。无论是查找还是修改 UI 方面的代码都应该是简单明了的，在理想情况下，我只需要管好我自己的 Modal 就好了

<!-- more -->

为了达成上述目标，我决定使用从未接触过的技术替换自己熟悉的技术栈，在整个过程中肯定会有大量的学习和思考，而这也是我要通过本文和各位分享的焦点。在下文中，我将会一一指出这些技术，然后做一些简单的介绍，最后就是实战演练。

## 技术栈概览

- React，与 Angular 和 Ember 的大而全不同，它更专注于视图层。React 使用 JSX 语法构建页面标签，这些标签被真实渲染到页面之前称为 virtual DOM。React 相当于代理开发者高效地处理页面渲染，减少重绘和回流，从而提高页面性能。简而言之，React 的优点就是优雅易用易上手
- Falcor，Netflix 开源的库，与传统的 REST API 提供精确、预定的数据不同，该库的思路是提供一个完整的数据，再由开发者向 API 服务器发送个性化的需求。
- Webpack：
- ES6：







































































###### 参考资料

- [The Future of Web Development - React, Falcor, and ES6](http://engineering.widen.com/blog/future-of-the-web-react-falcor/)
- [Full-Stack Automated JavaScript Testing](http://engineering.widen.com/blog/testing-future-web-stack/)