aave上面质押的加密货币与数量

c# 写一个函数，给一个op链地址，得到aave上面质押的加密货币与数量，以及质押率
ChatGPT
要编写一个函数来获取给定的 Aave 借贷协议上的质押信息，你可以使用 Aave 的 Subgraph API 来实现这个功能。Subgraph API 允许你查询 Aave 的智能合约数据，包括用户的质押信息。以下是一个简单的示例函数，假设你已经有了 Aave 的 Subgraph API 的访问权限：
确认最新的Aave Subgraph URL
首先，确认您使用的是最新的Aave Subgraph API URL。Aave通常有多个版本，常用的是V2和V3。
Aave V2 Subgraph URL: https://api.thegraph.com/subgraphs/name/aave/protocol-v2
Aave V3 Subgraph URL: https://api.thegraph.com/subgraphs/name/aave/protocol-v3
使用Postman或浏览器测试API URL
在继续编写C#代码之前，您可以使用Postman或浏览器测试这些URL是否有效。可以使用以下简单的GraphQL查询：

