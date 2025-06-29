Orm bp

Save as json file...
Qry also as json ...


淡化sql.默认表tblx

默认就是分库了。。。


这样无需idx查询。。

基本api几乎和json自定db模式一样了。。。

     Console.WriteLine(JsonConvert.SerializeObject(FLstrCls.qry("pinlunDir/ziluxwubxeaktvrvcmsrryfzrmH13json")));

   Console.WriteLine(JsonConvert.SerializeObject(ormSqlt.qry("pinlunDir/ziluxwubxeaktvrvcmsrryfzrmH1.db")));

如果是rds
save( mapx,  keyName)
超前的理念，需求领跑第一线，
如果未来需要更换资料库，使用ORM 可以轻松移植代码，而不需要大量修改。 提高安全性：ORM 可以通过防止SQL 注入攻击等方式，提高应用程式的 ...
orm统一的api
细化分库存储数据，就可以统一api了，不要使用sql去查询。去特定库表select all，在做搜索。。
               


 internal static void save(Hashtable mapx, string dbFileName)
 {
     var tblx = "tabx";
 //    _save("tabx", chtsSesss, strFL);

     var __METHOD__ = MethodBase.GetCurrentMethod().Name;
     dbgCls.setDbgFunEnter(MethodBase.GetCurrentMethod().Name, dbgCls.func_get_args(MethodBase.GetCurrentMethod(), tblx, mapx, dbFileName));

     //--------------------- crt table

     crtTable(tblx, mapx, dbFileName);



     var sql = $"replace into {tblx}" + sqlCls.arr_toSqlPrms4insert(mapx);
     dbgCls.setDbgVal(__METHOD__, "sql", sql);
     // Console.WriteLine(sql);
     SqliteConnection cn = new SqliteConnection("data source=" + dbFileName);
     cn.Open();

     SqliteCommand cmd = new SqliteCommand();
     cmd.Connection = cn;
     cmd.CommandText = sql;


     var ret = cmd_ExecuteNonQuery(cmd);
     dbgCls.setDbgValRtval(__METHOD__, ret);
 }



        public static List<Dictionary<string, object>> qry(  string dbFileName)
        {
            return _qry("select * from tabx", dbFileName);
        }


        /**
         * @param SQLite3 $db
         * @param string $querySql
         * @return array
         */
        public static List<Dictionary<string, object>> _qry(string querySql, string dbFileName)
        {
            // setDbgFunEnter(__METHOD__, func_get_args());
            var __METHOD__ = MethodBase.GetCurrentMethod().Name;
            dbgCls.setDbgFunEnter(__METHOD__, dbgCls.func_get_args(MethodBase.GetCurrentMethod(), querySql, dbFileName));

            SqliteConnection cn = new SqliteConnection("data source=" + dbFileName);
            cn.Open();
            //    SqliteCommand cmd = new SqliteCommand();
            //cmd.Connection = cn;
            //    cmd.CommandText = sql;
            //    cmd.ExecuteNonQuery


            var results = new List<Dictionary<string, object>>();
            using (var cmd = new SqliteCommand(querySql, cn))
            {
                using (var reader = cmd.ExecuteReader())
                {


                    while (reader.Read())
                    {
                        var row = new Dictionary<string, object>();
                        for (int i = 0; i < reader.FieldCount; i++)
                        {
                            row[reader.GetName(i)] = reader.GetValue(i);
                        }
                        results.Add(row);
                    }


                }
            }

            // 获取当前方法的信息
            //MethodBase method = );

            //// 输出当前方法的名称
            //Console.WriteLine("Current Method Name: " + method.Name);
          dbgCls.  setDbgValRtval(MethodBase.GetCurrentMethod().Name, dbgCls. array_slice(results, 0, 3));


            return results;
        }
