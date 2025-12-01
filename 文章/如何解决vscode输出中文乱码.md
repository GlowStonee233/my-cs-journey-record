# 分析
输出中文乱码，主要是因为编码不匹配
接下来将会将源文件与终端的编码都改为UTF8以解决乱码
# 修改源文件为UTF8
一般vscode创建的文件，编码都是UTF8，如果不是那就在右下角状态栏选择Save with encoding，改为用UTF8保存。平时如果打开文件遇到乱码时可以利用Reopen with encoding调整编码来解决问题
# 修改终端编码为UTF8
修改终端编码为UTF8，主要利用了以下命令：
```powershell
chcp 65001
```
但是如果每次运行都要输入这样一行命令的话，会很浪费时间。
## 更好的方法
如果你使用code runner的话，在setting.json文件的"code-runner.executorMap"处添加这样一行代码（以C语言为例）：
```
"c": "cd $dir; gcc -fexec-charset=UTF-8 '$fileName' -o '$fileNameWithoutExt'; if ($?) { chcp 65001 | Out-Null; .\\'$fileNameWithoutExt' }",
```
就可以解决乱码问题。
这个方法能解决问题关键在这一行命令：
```
if ($?) { chcp 65001 | Out-Null;
```
命令解释：

 `if ($?) { ... }`
- `$?`：PowerShell 的特殊变量，表示上一条命令的执行结果
- `$?` 为 `$true` 表示成功，`$false` 表示失败
- 只有编译成功（gcc 返回 0）才会执行花括号内的内容

`chcp 65001 | Out-Null`
- `chcp 65001`：Windows 命令，将控制台代码页设置为 65001（UTF-8）
- `| Out-Null`：PowerShell 的管道操作，将输出重定向到空设备（不显示任何信息）
# 一点问题
这样设置，虽然消除了编码更改的信息，但是有可能把powershell的提示符也给消除了。
推荐设置为以下：
```
"c": "cd $dir; gcc -fexec-charset=UTF-8 '$fileName' -o '$fileNameWithoutExt'; if ($?) { [Console]::OutputEncoding = [System.Text.Encoding]::UTF8; .\\'$fileNameWithoutExt' }",
```
这里使用 OutputEncoding 替代 chcp，防止影响到提示符。