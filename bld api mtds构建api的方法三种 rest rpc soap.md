

API 协议和架构 三类：REST、RPC 和 SOAP
===REST。表述性状态转移 ( REST ) 架构可能是构建 API 的最流行方法
===RPC。远程过程调用 (RPC) 协议
===当前使用的 API 示例
--社交媒体 API。
--登录和身份验证 API。
--小部件和服务 API。
--金融和支付 API。
--旅行和预订 API。
--运输和供应链 API。
--内容交付和管理 API。

API 协议和架构 三类：REST、RPC 和 SOAP
API 交换命令和数据，这需要明确的协议和架构——管理 API 操作的规则、结构和约束。如今，API 协议或架构有三类：REST、RPC 和 SOAP。这些可能被称为“格式”，每种格式都有独特的特性和权衡，并用于不同的目的。

===REST。表述性状态转移 ( REST ) 架构可能是构建 API 的最流行方法

。REST依赖于客户端/服务器方法，该方法将 API 的前端和后端分开，并在开发和实施方面提供了相当大的灵活性。REST 是无状态的，这意味着 API 在请求之间不存储任何数据或状态。REST 支持缓存，缓存会存储对慢速或非时间敏感 API 的响应。REST API（通常称为RESTful API）也可以直接通信或通过中间系统（如API 网关和负载均衡器）运行



===RPC。远程过程调用 (RPC) 协议

是一种发送多个参数并接收结果的简单方法。RPC API调用可执行操作或进程，而 REST API 主要交换数据或资源（例如文档）。RPC 可以使用两种不同的语言JSON和 XML 进行编码；这些 API 分别被称为JSON-RPC和XML-RPC


===当前使用的 API 示例
API 是许多现代软件平台成功的关键，甚至是必不可少的。日常计算机用户可能会使用各种各样的 API，但从未意识到它们的重要性。当代 API 用例的示例包括：

--社交媒体 API。
Twitter和 Facebook 等社交媒体平台依赖 API 来处理平台与远程端点之间的通信，包括 Twitter 机器人等功能。
--登录和身份验证 API。
当今高度集成的软件环境依赖 API 来提供某种程度的单点登录。例如，一个应用程序可能会要求用户“使用 Facebook 登录”。这样就无需用户为其使用的每个网站或应用程序创建唯一帐户，但所涉及的 API 可在后台有效地集成多个应用程序的身份验证。
--小部件和服务 API。
API通常用于集成各种小特性和功能。例如，网络搜索中出现的天气报告、海洋潮汐时间表、新闻提要和其他内容通常是通过搜索引擎向各种服务提供商使用的 API 生成的。其他服务（如 Google 地图）使用 API 使用户能够通过其网络浏览器搜索位置或规划路线，API 还允许将地图包含在无数第三方网站中。
--金融和支付 API。
银行依靠 API 将远程用户连接到银行的后端系统以进行远程存款、余额查询、转账和电子支付是很常见的事。PayPal 等大型金融企业使用 API 将用户连接到 PayPal 帐户，甚至使用 PayPal 向其他购物网站（如亚马逊和 eBay）付款。
--旅行和预订 API。
搜索航班时刻表和购买机票的用户使用航空公司的 API，而搜索酒店空房和预订房间则使用酒店的 API。其他网站（如 Trivago 和 Expedia）使用自定义API 让用户搜索和预订各种航班和住宿，而旅行网站则从后端使用航空公司、酒店、汽车租赁和其他提供商的 API。
--运输和供应链 API。
将物品从原产地包装并运送到目的地的过程会产生大量实时数据。API 用于让客户查看购买状态并查看任何运输详细信息，包括包裹的当前位置及其预计交付时间。
--内容交付和管理 API。
Spotify和 Netflix 等在线内容交付平台依靠 API 让用户选择所需内容，然后将该流媒体内容交付到用户的设备供用户观看，同时提供商保持对内容的控制，而这些内容实际上从未下载或存储在用户的设备上。
微服务。从软件开发的角度来看，API 是现代基于微服务的应用程序的重要元素，允许组成应用程序的众多模块或容器之间进行通信。因此，可以对一个模块进行更改，但测试和更新可以局限于相应的模块或微服务。