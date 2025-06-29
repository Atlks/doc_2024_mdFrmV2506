进入大厅的代码文档




bty-java-domas, [10/9/2024 4:52 PM]
后台创建用户貌似这个接口 
  // 调用方法
        GlGameUser actualUser = AbstractPtGameBaseGameApi1.createThirdGameUser(apiConfig, createDTO, header);

bty-java-domas, [10/9/2024 4:53 PM]
AbstractPtGameBaseGameApi1.createThirdGameUser（）



应该是这里了我看到url对应的方法了。。
/**
     * 游戏跳转： giGameController.java
     * @RequestMapping("/forehead/gamebet/game")
     * public class GlGameController extends GameBetBaseController {
     *  归集游戏钱包
     *  根据端缓存用户跳转链接
     */
    @RequestMapping(value = "/jump", method = {RequestMethod.POST, RequestMethod.GET})
    @IPAddressAnnotation
public Result jump(@Validated GameJumpParam gameJumpDO, @ModelAttribute(value = "userInfo", binding = false) GlUserDO user, HttpServletRequest request) throws GlobalException {


Ivk chain       
giGameController。Jump()
digitGameHdnler.gameJump()       digitalGameHandler.gameJump

* 获取进入游戏的链接
* GlGameBusiness.doGameUrlGenerate()      glGameBusiness.doGameUrlGenerate


 
 AbstractBaseGameApiImpl.doGameUserCreate（）

.  // 调用方法
        GlGameUser actualUser = AbstractPtGameBaseGameApi1.createThirdGameUser(apiConfig, 














* GlGameBusiness.doGameUrlGenerate()

GlGameUser gameUser = glGameUserBusiness.getGlGameUser(key);
if (gameUser == null) {
    log.info("当前的用户没有创建成功");
    gameUser = glGameApiHandler.doGameUserCreate(merchant, dto);
}


