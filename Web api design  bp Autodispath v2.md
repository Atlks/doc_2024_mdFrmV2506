Web api design  bp Autodispath 



Json file as api.. Path as query dsl

Just    /xxxx.json  as api
Path as query dsl

Qry str as qry dsl;
Autodispath 


 /*
      webapiStart((context) =>
     {
         var request = context.Request;
         string methd = request.Path;
       ////  methd = methd.Substring(1);
         if (methd == "/swag")
         {
             context.Response.ContentType = "text/html; charset=utf-8";
              var rzt= Wbapi_swagApi("mdsj.xml");
             context.Response.WriteAsync(rzt.ToString(), Encoding.UTF8).GetAwaiter().GetResult();
             jmp2end();
         }
                  
     });
         
  */
 /// <summary>
 /// /
 /// </summary>
 /// <param name="act"></param>
 public static void webapiStart(Action<HttpContext> act)
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
     //拦截请求：
     app.Run(async (HttpContext context) =>
     {
         try
         {
             // 获取当前请求的 URL
             var request = context.Request;
             var url = $"{request.Scheme}://{request.Host}{request.Path}{request.QueryString}";

             // 获取查询字符串
             var queryString = request.QueryString.ToString();
             string methd = request.Path;

             // 设置响应内容类型和编码
             context.Response.ContentType = "application/json; charset=utf-8";

             act(context);
             methd = methd.Substring(1);
             object rzt = callxTryx("Wbapi_" + methd, Substring(queryString, 1));
             //   context.Response.ContentEncoding = Encoding.UTF8;
             await context.Response.WriteAsync(rzt.ToString(), Encoding.UTF8);
         }
         catch (jmp2endEx e)
         {
         }
         catch (Exception e)
         {
             print_catchEx(nameof(webapiStart), e);
             logErr2025(e, nameof(webapiStart), "errlog");
         }

     });
     app.Run();
 }
