Web3 wlt algo


C:\0prj\paymentJava2024\lib\ky2add.dart
C:\0prj\paymentJava2024\src\main\java\ky2add.java

Object? getEthAddByKyRaw(String kyRaw) {

  String Entropy1 =md5Hash(kyRaw)  ;
 // var mmnc = getMmnc(Entropy1);
  var mmnc = getMmnc(Entropy1);
  // print("mmnc:"+mmnc);
  var mnemonicToPrivateKeyHex2 = mnemonicToPrivateKeyHex(mmnc);
  //  print("key Frm mmnc:"+mnemonicToPrivateKeyHex2);
  return getEthereumAddress(mnemonicToPrivateKeyHex2);
  String ethAddress = getEthAddByEntropy128b(Entropy1);
  print('Ethereum Address: $ethAddress');

}
String getEthAddByEntropy128b(String privateKey) {
  var mmnc = getMmnc(privateKey);
  // print("mmnc:"+mmnc);
  var mnemonicToPrivateKeyHex2 = mnemonicToPrivateKeyHex(mmnc);
 //  print("key Frm mmnc:"+mnemonicToPrivateKeyHex2);
  return getEthereumAddress(mnemonicToPrivateKeyHex2);
}

