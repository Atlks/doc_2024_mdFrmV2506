Dsl 查询引擎的实现 api  与存储引擎的api

存储引擎是针对表的而不是库，对于同一个库不同的表可以使用不同的存储引擎。

据用各种不同的方式存储在文件（或内存）中，每一种存储的方式都使用不同的存储机制，索引技巧等，最终提供广泛的不同功能和能力

存储引擎不能解析SQL，互相之间也不能通信。仅仅是简单的响应服务器的请求。
第16章：编写自定义存储引擎


查询引擎   qry分区支持 （wehere，order，select条件）




Qry单个分区+wehre条件

order，select条件都不要


Rd（dbf ）存储引擎。。只负责读取数据。。


mysql的存储引擎api


通过索引访问table内容  
索引可以存在存储引擎，也可单独存储。。存储格式可以hot，也可以iot
，ye'k'y索引前调用该方法
int ha_foo::index_init(uint keynr, bool sorted) 
对表加锁：
当客户端调用LOCK TABLE时，通过external_lock函数加锁：
int ha_example::external_lock(THD *thd, int lock_type)
全表扫描：
//初始化全表扫描
virtual int rnd_init (bool scan);




        //parti spt
        private static List<SortedList> qry(string dataDir, string partnsExprs,
            Func<SortedList, bool> whereFun, Func<SortedList, int> ordFun=null,
                Func<SortedList, SortedList> selktFun= null)
        {
            List<SortedList> rztLi = new List<SortedList>();
            var patns_dbfs = db.calcPatnsV2(dataDir, partnsExprs,"db");
            string[] arr = patns_dbfs.Split(',');
            foreach (string dbf in arr)
            {
                List<SortedList> li = _qryBySnglePart(dbf, whereFun);
                rztLi = arrCls.array_merge(rztLi, li);
            }

            return rztLi;
        }

        //单个分区ony need where ,,,bcs order only need in mergeed...and map_select maybe orderd,and top n ,,then last is need to selectMap op
        public static List<SortedList> _qryBySnglePart(string dbf, Func<SortedList, bool> whereFun)
        {
            List<SortedList> li = rdFrmStoreEngr(dbf);

            li = db.qryV7(li, whereFun, null, null);
            return li;
        }

        private static List<SortedList> rdFrmStoreEngr(string dbf)
        {
            SortedList prm = new SortedList();

            //   prm.Add("partns", ($"{mrchtDir}\\{partns}"));
            prm.Add("dbf", ($"{dbf}"));

            string timestamp2 = DateTime.Now.ToString("yyyyMMdd_HHmmss_fff");
            Directory.CreateDirectory("prmDir");
            File.WriteAllText($"prmDir/prm{timestamp2}.txt", json_encode(prm));

            string prm_fileAbs = GetAbsolutePath($"prmDir/prm{timestamp2}.txt");

            string prjDir = @"../../";
            string str = ExecuteNodeScript($"{prjDir}\\sqltnode\\qry.js", prm_fileAbs);
            string marker = "----------qryrzt----------";
            str = ExtractTextAfterMarker(str, marker);
            str = str.Trim();
            string txt = File.ReadAllText($"{prjDir}\\sqltnode\\tmp\\" + str);
            List<SortedList> li = json_decode(txt);
            return li;
        }



