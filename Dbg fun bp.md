Dbg fun bp



Outputfmt AS CODE LOG AS CODE

FUN XXX()
ENDFUN XXX()

GetCurrentMethod
var __METHOD__ = MethodBase.GetCurrentMethod().Name;


func_get_args

在 PHP 中，func_get_args 函数用于获取传递给函数的所有参数。C# 中没有直接等效的内置函数，但可以通过使用参数数组（params 关键字）来实现类似的功能。
以下是一个示例，展示了如何在 C# 中实现类似于 func_get_args 的功能，获取传递给函数的所有参数并将其返回为一个对象数组
使用 params object[] parameters 声明参数数组，这允许传递任意数量和类型的参数。

        public static object func_get_args(MethodBase method, params object[] paramValues)
        {
            // 获取当前方法
           // MethodBase method = new StackFrame(1).GetMethod();

            // 获取当前方法的参数
            ParameterInfo[] parameters = method.GetParameters();

            // 获取当前方法的参数值
            // 将参数名称和值配对
            var parameterValues = parameters.Select((p, index) => new
            {
                p = p.Name,
                v = paramValues[index]
            }).ToList();
            return parameterValues;
            // 序列化为 JSON 字符串
            //  return JsonConvert.SerializeObject(parameterValues, Formatting.Indented);
        }
