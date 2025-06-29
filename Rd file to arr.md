Rd file to arr


在PHP中读取文件到数组的常见方法是使用内置的 file() 函数。该函数将文件的每一行读取为数组的一个元素。
以下是如何使用 file() 函数读取文件内容并将其存储到数组中的示例：

C#   File.ReadAllLines(filePath);

Go

// 使用 bufio.Scanner 逐行读取文件 scanner := bufio.NewScanner(file) for scanner.Scan() { lines = append(lines, scanner.Text()) }


Java 
// 使用 Files.readAllLines() 方法将文件内容读取到列表中 return Files.readAllLines(Paths.get(filePath));
