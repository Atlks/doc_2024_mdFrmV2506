.net add web api


webapi
ChatGPT
在一个现有的 .NET 8 项目中实现一个最简单的 Web API，你可以使用 Minimal API 的方式。这是 .NET 6 引入的一种方式，让你可以快速创建一个轻量级的 Web API。
以下是如何在你的现有 .NET 8 项目中实现一个简单的 Web API 接口，接受 getlist 参数并返回 "OK" 的步骤：

确保你已经有一个 .NET 8 项目： 确保你已经有一个现有的 .NET 8 项目。如果还没有，可以使用以下命令创建一个新的空项目：


bash


Copy code


要在你的 .NET 8 Web API 项目中自定义端口，可以在 Program.cs 文件中配置 Kestrel 服务器的监听端口。你可以在创建 WebApplicationBuilder 时进行设置。以下是如何实现的示例：

完整的 Program.cs 文件：
csharp
Copy code
using Microsoft.AspNetCore.Builder;using Microsoft.AspNetCore.Http;using Microsoft.Extensions.Hosting;
var builder = WebApplication.CreateBuilder(args);var app = builder.Build();

app.MapGet("/getlist", (HttpContext context) => {
    var getlist = context.Request.Query["getlist"];
    Console.WriteLine("Received getlist: " + getlist);
    return Results.Ok("OK");
});

app.Run();




  private static void webapiStart()
  {
      var builder = WebApplication.CreateBuilder();

      // Configure Kestrel to listen on a specific port
      builder.WebHost.ConfigureKestrel(serverOptions =>
      {
          serverOptions.ListenAnyIP(5001); // 自定义端口号，例如5001
      });
      var app = builder.Build();

      //http://localhost:5000/api?callGetlistFromDb=yourValue11
      app.MapGet("/api", (string callGetlistFromDb,string 园区=null,int page=1) => {
          Console.WriteLine("Received getlist: " + callGetlistFromDb);
          //  return Results.Ok("OK");
          SortedList map = new SortedList();
          map.Add("limit", 5);
          var list = getListFltr("mercht商家数据", null, null);
          int start = (page - 1) * 10;

          list = list.Slice(start, 10);
          return encodeJson(list);
      });

      app.Run();
  }
