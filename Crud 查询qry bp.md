Crud 查询qry bp


最好使用索引模式直接查询
Path作为dsl来直接定位记录。。。
使用文件名作为索引 查询的时候直接判断exist即可了。。
写入数据的时候，直接就索引模式了



。。不要使用where条件麻烦。。


写入数据的时候，直接就索引模式了

使用文件名作为索引
      //记录拉如机器人记录，谁拉到哪个群了。。未来权限判断
      var grpid = update.MyChatMember.Chat.Id;
      var uid = update.MyChatMember.From.Id;
      var botNme = update.MyChatMember.NewChatMember.User.Username;
      System.IO.File.WriteAllText(json_encode(update), $"botEnterGrpLog/{grpid}.{uid}.{botNme}.json");
              


查询的时候直接判断exist即可了。。

Id查询大部分是，使用索引模式即可
联合索引  grp{grpid}.U{uid}.addBot.{botname}.json

复杂的查查下使用wherer模式
