进入大厅同时金钱转移的逻辑总结


大概是先生产用户，同步到三方。。然后调用上分接口给三方充值，然后返回大厅的url准备跳转，，这样用户进入三方大厅的时候就有了金钱可以玩和游戏了




/jump

C:\0prjNtpc\digital-bet-service - p3\st-gamebet\gamebet-service\src\main\java\com\seektop\gamebet\controller\forehead\GlGameController.java
/**
 * 游戏跳转：
 *  归集游戏钱包
 *  根据端缓存用户跳转链接
 */
 public Result jump( )  





C:\0prjNtpc\digital-bet-service - p3\st-gamebet\gamebet-common\target\classes\com\seektop\gamebet\common\business\GlGameBusiness.class
/**
 * 获取进入游戏的链接
 *
 
 */
doGameUrlGenerate(）

if( game.getChannelId()==GameChannelConstants.CHANNEL_EVO)//evo
{
    //这里要给转账给游戏  bef enter game
    return getresultDTO4evoByCfgmng(userDO, "evo"+gameJumpDto.getCoinCode(),   stNacosConfigManager,resultDTO);
}






getresultDTO4evoByCfgmng（）{
  getresultDTO4evo(userDO, configSourceStr, resultDTO);
    //trans 这里转移金钱
    transBanlance2game(userDO, configSourceStr);
    return resultDTO1;

}





