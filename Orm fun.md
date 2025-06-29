Orm fun


返回结果可能几种，，list ，obj ，某个fld val


  List list=session.createQuery(hql).setString(0, id).list(); 
  //User user =(User) query.uniqueResult(); //当确定返回的实例只有一个或者null时 用uniqueResult()方法



添加一条数据
可以使用save方法统一写入数据，自动判断是新增还是更新数据（以写入数据中是否存在主键数据为依据）。
更新数据
可以使用save方法更新数据




查询单个数据
查询单个数据使用find方法：
find方法查询结果不存在，返回 null，否则返回结果数组

值和列查询
查询某个字段的值可以用
// 返回某个字段的值
Db::table('think_user')->where('id', 1)->value('name');
自增/自减
可以使用inc/dec方法自增或自减一个字段的值（ 如不加第二个参数，默认步长为1）。
delete方法返回影响数据的条数，没有删除返回 0
