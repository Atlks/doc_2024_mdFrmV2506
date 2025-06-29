c# .net 获取当前方法的参数，序列化为json字符串

在 PHP 中，func_get_args 函数用于获取传递给函数的所有参数。C# 中没有直接等效的内置函数，但可以通过使用参数数组（params 关键字）来实现类似的功能。
以下是一个示例，展示了如何在 C# 中实现类似于 func_get_args 的功能，获取传递给函数的所有参数并将其返回为一个对象数组
使用 params object[] parameters 声明参数数组，这允许传递任意数量和类型的参数。

ChatGPT
在 C# 中，你可以使用反射来获取当前方法的参数，然后将这些参数序列化为 JSON 字符串。要实现这一点，可以结合使用 System.Reflection 命名空间和 Newtonsoft.Json 库（也称为 Json.NET）来完成。
使用 StackFrame 获取当前方法的 MethodBase。
获取当前方法的参数信息。
使用 LINQ 获取参数名称和参数值。
使用 JsonConvert.SerializeObject 将参数名称和值序列化为 JSON 字符串。
使用 params object[] paramValues 参数收集传递的实际参数值。

这里实际的参数值只能手动传入，不能自动获取，不像php

      dbgCls.setDbgFunEnter(__METHOD__, dbgCls.func_get_args(MethodBase.GetCurrentMethod(), querySql, dbFileName));

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



