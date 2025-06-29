C# 文档生成总结


Xml文件阅读不便。。

可以写个函数将xml转换为html
即可。


M:mdsj.libBiz.apiBiz.Wbapi_getlist(System.String)
功能 : 查询商家
范例: http://localhost:5000/getlist?id=avymrhifuyzkfetlnifryraazk
范例: http://localhost:5000/getlist?分类=娱乐&page=1
----参数 id: 商家id
----参数 分类: 商家分类
----参数 page: 页数
----参数 pagesize: 每页数量
返回值 : 返回json数组.




       public static void ConvertXmlToHtml(string xmlFilePath, string htmlFilePath)
       {
           var sb = new StringBuilder();

           sb.AppendLine("<html>");
           sb.AppendLine("<head><title>XML Documentation</title></head>");
           sb.AppendLine("<body>");
           sb.AppendLine("<h1>api文档</h1>");

           using (var reader = XmlReader.Create(xmlFilePath))
           {
               while (reader.Read())
               {
                   if (reader.NodeType == XmlNodeType.Element && reader.Name == "member")
                   {
                       string name = reader.GetAttribute("name");
                       sb.AppendLine($"<h2>{name}</h2>");

                       while (reader.Read() && !(reader.NodeType == XmlNodeType.EndElement && reader.Name == "member"))
                       {
                           if (reader.NodeType == XmlNodeType.Element)
                           {
                               string elementName = reader.Name;
                               if (elementName == "example")
                               {
                                   reader.Read(); // Move to the text node or CDATA
                                   if (reader.NodeType == XmlNodeType.CDATA || reader.NodeType == XmlNodeType.Text)
                                   {
                                       string exampleText = reader.Value;
                                       sb.AppendLine($"<p><strong>范例:</strong> {exampleText}</p>");
                                   }
                               }
                               else
                               {
                                   string prmname = reader.GetAttribute("name");
                                   SortedList stlst = new SortedList();
                                   stlst.Add("summary", "功能");

                                   stlst.Add("returns", "返回值");
                                   stlst.Add("param", "----参数");
                                   reader.Read(); // Move to the text node

                                   if (reader.NodeType == XmlNodeType.Text)
                                   {
                                       string text = reader.Value;

                                       sb.AppendLine($"<p><strong>{stlst[elementName]+"  " + prmname}:</strong> {text}</p>");
                                   }
                               }

                           }
                       }
                   }
               }
           }

           sb.AppendLine("</body>");
           sb.AppendLine("</html>");

           System.IO.File.WriteAllText(htmlFilePath, sb.ToString());
       }


