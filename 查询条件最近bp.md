查询条件最近bp

把条件全部组成一个list

每个条件都是bool类型，只要


  List<Condtn> li = new List<Condtn>();
  li.Add(new Condtn(isNotEmptyLianxi(row)));
  li.Add(new Condtn(isLianxifshValid(row)));
  li.Add(new Condtn(isFldValEq111(row, "城市", whereExprsObj)));
  li.Add(new Condtn(isFldValEq111(row, "园区", whereExprsObj)));
  li.Add(new Condtn(isFldValEq111(row, "国家", whereExprsObj)));
  li.Add(new Condtn(isCotainFuwuci(row, msgCtain)));
  li.Add(new Condtn(msgHasPostWd && isCotainPostnWd(row, kwds)));
  if (!ChkCdtAllTrue(li))
      return false;

最后只要chk any faslse 返回去即可。。
