Tp use v2


<?php

// tpuse.php
require __DIR__ . '/../vendor/autoload.php';
require_once __DIR__ . "/../lib/ex.php";
loadErrHdr();



require_once __DIR__ . "/../config/console.php";
imptTplib();

// composer update topthink/framework
var_dump(9999);
$rows_dxds = \think\facade\Db::query("select * from db1.t1  ");
var_dump($rows_dxds);


var_dump($rows_dxds[1]['c1']);







................................


<?php


//   config/console.php

if(!class_exists("imptTp1129"))
{
    class imptTp1129 extends think\console\Command
    {
        protected function configure()
        {
            $this->setName('.');
        }

        protected function execute(think\console\Input $input, think\console\Output $output)
        {
            //$output->writeln("TestCommand:");
            var_dump(111);
        }
    }

}


if(!function_exists("imptTplib"))
{
    function imptTplib()
    {

        // 应用初始化导入tp类库
        $console = (new \think\App())->console;
// $console->$catchExceptions=false;  dflt jst fas..
        $console->call("导入TP类库");
    }
}


// +----------------------------------------------------------------------
// | 控制台配置
// +----------------------------------------------------------------------
return [
    // 指令定义
    'commands' => [


        'keywdReqHdlr' => 'app\common\keywdReqHdlr',
        'msgHdlrLhc' => 'app\common\msgHdlrLhc',


        'imptTp' => '\imptTp1129',
        '导入TP类库' => '\imptTp1129',


    ],
];

