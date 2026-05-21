

* vscode扩展批量复制迁移到新配置

在老配置下终端：
```
code --list-extensions > extensions.txt
```

把extensions.txt拖到新项目目录，输入命令：
```
Get-Content extensions.txt | ForEach-Object {
  code --install-extension $_ --profile "新配置文件名"
}