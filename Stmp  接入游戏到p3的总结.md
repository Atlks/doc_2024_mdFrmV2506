Stmp  接入游戏到p3的总结


通过接入evo真人游戏的总结 
目前p3 增加游戏需要增加架构5层的此代码
Controller 层GlGameController .jump()
Handler层   digitalGameHandler.gameJump（）
Business.层GlGameBusiness.doGameUrlGenerate()   
Api层   apihandelr层
Api父类

增加配置
 数据表四个表增加channel配置
  #  gl_game.sql
  /*
  
  gl_game_channel.sql
gl_game_mainten.sql
gl_game_merchant.sql
gl_game_show_config.sql
增加nacos配置

Nacos 配置  global-game-info 增加一个游戏的channel   

具体游戏的相关coin配置是保存在  global-game-api-config。。这个文件太大太多配置，可以单独建立key增加稳定性，防止修改造成影响其他的问题。。


  这里以  evoCNY为key，新建立一个游戏币种配置


Java代码增加

增加GlEVORealGameApiHandlerImpl.

C:\0prjNtpc\digital-bet-service - p3\st-gamebet\gamebet-common\src\main\java\com\seektop\gamebet\common\handler\digitalgame\GlEVORealGameApiHandlerImpl.java


调整 GlGameBusiness.doGameUrlGenerate()
增加对特定channenl游戏的业务处理

理论上这个业务类里面就可以通过调用api接口返回url，但代码量较多，这部分代码转移到另外一个EvoBusiness里面去了即可

具体代码就是读取nacos的配置的  游戏币种配置，去三方api请求创建用户以及返回进入大厅的链接。。




后台配置游戏维护与场馆维护添加


前端 》真人  会出现所再的游戏

