Api 文档




查询商家
 http://localhost:5000/getlist?分类=娱乐&page=1&pagesize=2

返回数据

[
  {
    "Comments": "{\r\n  \"879006550\": \"评论\"\r\n}",
    "Guid编号": "aavmyftvhqbujniooatlecvwam",
    "Line": "[]",
    "Promotion": "",
    "Scores": "{}",
    "Searchs": "226",
    "Signal": "[]",
    "TG有效": null,
    "Tel": "[]",
    "Telegram": "[\r\n  \"ddhs888\"\r\n]",
    "Views": "11",
    "WhatsApp": "[]",
    "_parent": "妙瓦底_KK园区",
    "cateEgls": "Club",
    "cateInt": "6",
    "id": "aavmyftvhqbujniooatlecvwam",
    "ord": "0",
    "关键词": "KTV 帝诗 shangjia 菜单 shop ktv 2楼",
    "分类": "娱乐",
    "分类关键词": "商家 ShangJia 菜单 前台 客服 菜单 Shop 店 红楼 二楼 嫖娼 妓女 妹子 鸡婆 会所 正规 按摩 掏耳 推拿 精油 全套 半套 快餐 泰式 中式 妈妈桑 会所 小姐 上门服务 水疗 桑拿 莞式 模特 技师 外围 大保健 洗脚 卡拉OK 唱歌 麦克风 预定 团建 酒水 卡拉OK 派对 伴唱 对唱 量贩 K歌 包厢 坐台 娱乐城 酒吧 喝酒",
    "分类编号": "6",
    "商家": "KTV 二楼 帝诗 会所",
    "园区": "KK园区",
    "园区关键词": "KK kk AA aa 园区 園區",
    "国家": "缅甸",
    "城市": "妙瓦底",
    "城市关键词": "妙瓦底 秒洼地 秒窪地 苗瓦迪",
    "开始时间": "00:00:00",
    "微信": "[]",
    "纸飞机群": "",
    "结束时间": "23:59:00",
    "菜单": "",
    "营业开始时间": null,
    "营业结束时间": null,
    "谷歌地图": ""
  }
]


商家详情
http://localhost:5000/getlist?id=avymrhifuyzkfetlnifryraazk

返回数据

[
  {
    "Comments": "{\r\n  \"879006550\": \"评论\"\r\n}",
    "Guid编号": "aavmyftvhqbujniooatlecvwam",
    "Line": "[]",
    "Promotion": "",
    "Scores": "{}",
    "Searchs": "226",
    "Signal": "[]",
    "TG有效": null,
    "Tel": "[]",
    "Telegram": "[\r\n  \"ddhs888\"\r\n]",
    "Views": "11",
    "WhatsApp": "[]",
    "_parent": "妙瓦底_KK园区",
    "cateEgls": "Club",
    "cateInt": "6",
    "id": "aavmyftvhqbujniooatlecvwam",
    "ord": "0",
    "关键词": "KTV 帝诗 shangjia 菜单 shop ktv 2楼",
    "分类": "娱乐",
    "分类关键词": "商家 ShangJia 菜单 前台 客服 菜单 Shop 店 红楼 二楼 嫖娼 妓女 妹子 鸡婆 会所 正规 按摩 掏耳 推拿 精油 全套 半套 快餐 泰式 中式 妈妈桑 会所 小姐 上门服务 水疗 桑拿 莞式 模特 技师 外围 大保健 洗脚 卡拉OK 唱歌 麦克风 预定 团建 酒水 卡拉OK 派对 伴唱 对唱 量贩 K歌 包厢 坐台 娱乐城 酒吧 喝酒",
    "分类编号": "6",
    "商家": "KTV 二楼 帝诗 会所",
    "园区": "KK园区",
    "园区关键词": "KK kk AA aa 园区 園區",
    "国家": "缅甸",
    "城市": "妙瓦底",
    "城市关键词": "妙瓦底 秒洼地 秒窪地 苗瓦迪",
    "开始时间": "00:00:00",
    "微信": "[]",
    "纸飞机群": "",
    "结束时间": "23:59:00",
    "菜单": "",
    "营业开始时间": null,
    "营业结束时间": null,
    "谷歌地图": ""
  }
]





打分接口

 http://localhost:5000/dafen?shangjiaID=yourValue11&dafen=3&uid=007

评论接口

http://localhost:5000/pinlun?shangjiaID=avymrhifuyzkfetlnifryraazk&pinlun=465464564646


参数说明  shangjiaID 商家id

Pinlun  评论内容



api文档
M:mdsj.libBiz.apiBiz.Wbapi_dafen(System.String)
功能 : 打分
范例: http://localhost:5000/dafen?shangjiaID=yourValue11&dafen=3&uid=007
----参数 shangjiaID: 商家id
----参数 dafen: 分数
----参数 uid: 用户id
M:mdsj.libBiz.apiBiz.Wbapi_pinlun(System.String)
功能 : 评论商家
范例: http://localhost:5000/pinlun?shangjiaID=avymrhifuyzkfetlnifryraazk&pinlun=465464564646
----参数 shangjiaID: 商家id
----参数 pinlun: 评论内容
M:mdsj.libBiz.apiBiz.Wbapi_getlistPinlun(System.String)
功能 : 查询评论
范例: http://localhost:5000/getlistPinlun?shangjiaID=avymrhifuyzkfetlnifryraazk
----参数 shangjiaID: 商家id
返回值 : 返回json数组.
M:mdsj.libBiz.apiBiz.Wbapi_getlist(System.String)
功能 : 查询商家
范例: http://localhost:5000/getlist?id=avymrhifuyzkfetlnifryraazk
范例: http://localhost:5000/getlist?分类=娱乐&page=1
----参数 id: 商家id
----参数 分类: 商家分类
----参数 page: 页数
----参数 pagesize: 每页数量
返回值 : 返回json数组.

