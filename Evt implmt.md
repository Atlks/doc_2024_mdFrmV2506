Evt drv implmt  

C:\0prj\paymentJava2024\im\utilEvt.dart


Sub ---

Publish and subscribe patterns



//reg evt
addEventHandler("send",save2frbs);


// 添加事件处理函数
void addEventHandler(String evt, Function handler) {
  // 如果该事件没有处理函数列表，则初始化一个新的列表
  if (evtMap[evt] == null) {
    evtMap[evt] = [];
  }
  // 将处理函数添加到事件列表中
  evtMap[evt]?.add(handler);
}

Map<String, List<Function>> evtMap= {};

void trigEvt(String evt, Map<String, dynamic> m) {

  // process evt
  List<Function>? evtHdlrs=evtMap[evt];
  for(Function evtHdl in evtHdlrs!){
    evtHdl(m);
  }

}


