Prgrm design bp 2025 sumup

方法论

7. 元编程
代码生成、反射等元编程技术，提高了代码的灵活性。
**领域特定语言（DSL）**的开发，使得编程更贴近领域问题。
. 类型系统的发展
静态类型检查的加强，提高了代码的可靠性。
动态类型语言的类型推断能力增强，提高了开发效率。
类型系统与函数式编程的结合，产生了更强大的类型系统。

AI辅助  建立自己的codelib
利用chatgpt翻译代码建立标注算法
中文标成伪代码翻译模式
Basic top 100 fun 方便代码提示

函数分类


bsc cmd fun lgc argo.xlsx

Ui bp im ui
Txt h5 as ui dsl
Im msg evt
msgHdlr mode
          //------hi xiaongai txye xxx 
          callTryAll(() =>
          {
              string[] a = splt(update?.Message?.Text);
              a = trimUper(a);
              var cmd = getElmt(a, 1);
              var hdlrname = "msgHdlr" + serchTipsWd + cmd;
              callx(hdlrname, update);
          });


Autodispath ...   parse cmd,  call    xxxHdlr_cmd(qrystr)

Data stroe  json
Share tek
Ini  sqlt
Sqlt orm 表格kv化
Auto crt table lib 
Db as json file rw api

Table design

Use share，，，
Then  统一都是table1名字。字段只有一个 id， text  ，里面存放json数据即可。。

通过orm读取即可。。

这样就不需要自动化建表和加字段加索引了。
Db api  save del update wrteRow
Api规范来自orm和存储引擎


Doc teck
Doc as code 
读取注释解析
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

Oterh
Web api 

Web api design  bp Autodispath 
统一接货api，在读取path，call （path，context）转发派发


Log as code fmt
Fun naming api

函数管理函数分类的方法

分类法，每个分类元素大概10个左右比较好

目录
1. 控制类top10	1
2. Load get 系列 top10	1
3. 按照动作归类  约50个	1
3.1. 判断比较系列 Is系列 。。。Cmp系列	1
3.2. CastToxxx  convertToStr系列 ToStr系列。。Encode decode系列	1
3.3. io系列 Load get read wrt系列	1
4. Oo归类  top50	2
4.1. 针对数字，字符串，时间操作	2
4.2. 针对集合的操作  crud  数组 对象 hashtable操作的函数	2
4.3. 针对文件操作	2


未来编程语言的重大新特性展望

