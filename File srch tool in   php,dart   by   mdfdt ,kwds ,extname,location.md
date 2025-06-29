File srch tool in   php,dart   by   mdfdt ,kwds ,extname,location

jsPrjMng/lib/fulltxtSrchV2.php

C:\0prj\paymentJava2024\tool\srch.dart

void main() async {
  var mdfDate = '2020-11-11';
  final modifiedAfter = DateTime.parse(mdfDate); // 指定日期
  var sourceDirPath = 'C:\\0prjNtpc\\digital-bet-service'; // 主目录路径
  var targetDirPath = '/bkPrjDBS241108'; // 输出目录路径
  sourceDirPath = "C:\\0prjNtpc\\digital-bet-service - p3";
  targetDirPath = "bkPrjDBS241112asrch";
  var extnames = "java,xml";
  var srchKwds = "global-game-api-config";
  await srch(modifiedAfter, extnames, sourceDirPath, targetDirPath, srchKwds);
}

