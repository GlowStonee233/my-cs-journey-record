# 插件配置
Code Runner:Ignore Selection，禁用运行部分代码
Code Runner:Run In Terminal，在终端中运行
Code Runner: Save File Before Run，在运行前保存
Editor: Format On Type自动格式化，调整缩进对齐等
以上均设为true
Editor: Accept Suggestion On Commit Character
设为false，避免换行时补全
code runner setting.json文件，"code-runner.executorMap"中
添加了
```
"c": "cd $dir; gcc -fexec-charset=UTF-8 '$fileName' -o '$fileNameWithoutExt'; if ($?) { chcp 65001 | Out-Null; .\\'$fileNameWithoutExt' }",
```
和
```
"cpp": "cd $dir; g++ -fexec-charset=UTF-8 '$fileName' -o '$fileNameWithoutExt'; if ($?) { chcp 65001 | Out-Null; .\\'$fileNameWithoutExt' }",
```

