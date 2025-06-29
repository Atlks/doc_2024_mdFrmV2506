Php 遍历压缩包与读取文件


PHP 读取压缩包

Zip.numfiles()
读取文件 zip.getstream()

// 压缩包
$name = 'test.zip';
// 创建压缩包操作对象
$zip = new ZipArchive;
// 打开压缩包
$result = $zip->open($name);
if ($result === ZipArchive::ER_NOENT) {
    throw new \Exception("压缩包不存在");
} else if ($result !== true) {
    throw new \Exception("压缩包打开失败");
}
// 将压缩包文件解压到指定目录
$zip->extractTo('unzip');
// 在 TP6 中建议解压到 runtime 目录下
// $zip->extractTo(runtime_path() . 'unzip');

// 如果需要处理压缩包中的文件,遍历解压缩目录下的文件进行处理即可

// 释放压缩包对象
$zip->close();

