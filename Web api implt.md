Web api implt bp

      //拦截所有请求：然后自动给分发到 hdlr

    object rzt = callxTryx("Wbapi_" + methd, queryString.Substring(1));

Dont use mualt n ifelese struts...



  public static void webapiStart()
  {
      var builder = WebApplication.CreateBuilder();

      // Configure Kestrel to listen on a specific port
      ConfigureWebHostBuilder webHost = builder.WebHost;
      webHost.ConfigureKestrel(serverOptions =>
      {
          serverOptions.ListenAnyIP(5000); // 自定义端口号，例如5001
      });
      var app = builder.Build();

      //http://localhost:5000/dafen?callGetlistFromDb=yourValue11



      //拦截所有请求：
      app.Run(async (HttpContext context) =>
      {
          // 获取当前请求的 URL
          var request = context.Request;
          var url = $"{request.Scheme}://{request.Host}{request.Path}{request.QueryString}";

          // 获取查询字符串
          var queryString = request.QueryString.ToString();
          string methd = request.Path;
          methd = methd.Substring(1);
          object rzt = callxTryx("Wbapi_" + methd, queryString.Substring(1));
          await context.Response.WriteAsync(rzt.ToString());
      });
      app.Run();
  }

