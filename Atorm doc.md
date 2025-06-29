Atorm doc




Atlks/jsPrjMng · lib/db_sqlt.php

PHP

·

main





function save($tabl, $map, $dbFileName)
{
    setDbgFunEnter(__METHOD__, func_get_args());

    //--------------------- crt table

    @crtTable($tabl, $map, $dbFileName);

    $db = new SQLite3($dbFileName);
    $sql = "replace into $tabl" . arr_toSqlPrms4insert($map);
    setDbgVal(__METHOD__, "sql", $sql);
    $ret = $db->exec($sql);
    setDbgRtVal(__METHOD__, $ret);

}

