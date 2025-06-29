Smp dsn  remv mvc



MVC是一种与UI相关的模式。如果您正在构建一个复杂的应用程序，您应该从MVC三胞胎到任何其他类、子系统或层中获取与UI无关的所有内容。
这是我最大的错误。我花了很长时间来理解这个简单的规则：
不要在整个应用程序中传播MVC模式，
只限于与UI相关的内容。

随着像Backbone.js这样的前端MVC框架的流行，Struts这样的服务器端MVC的作用似乎有所减弱，您觉得MVC逻辑“前移”会是今后的发展趋势么？



我完全赞同这一点。在我参与的上一个项目中，对于服务端的Web层而言，几乎就成为了一个Controller+JSON+REST的组合，MVC中的M被JSON或资源所替代，V则干脆消失了，由Controller来负责必要的服务端验证，并完成HTTP请求的路由功能，其余的前端逻辑都交由我们



、当前端工程师拿走MVC的职责之后，自然会把MVC模式改成更适合前端的模式：MVVM。


不是Struts没了，也不是SpringMVC没了，而是MVC这种架构模式被淘汰了。当时代抛弃你时，连一声再见都不会说。


所以为了解决这个问题，MVVM就闪亮登场了。他把View和Contrller都放在了View层(相当于把Controller一部分逻辑抽离了出来)，Model层依然是服务端返回的数据模型。而ViewModel充当了一个UI适配器的角色，也就是说View中每个UI元素都应该在ViewModel找到与之对应的属性。除此之外，从Controller抽离出来的与UI有关的逻辑都放在了ViewModel中，这样就减轻了Controller的负担。
