### 执行命令并等待下个命令
```
@echo on
C:\Windows\System32\curl.exe -s -f -o --data-urlencode "keyword=1" "http://www.400537.com/code/callback/" & echo.
@cmd /k
```

### 循环执行curl，保存为bat文件
```
:next
C:\Windows\System32\curl.exe -s -f --output ".\curl_%date:~0,4%%date:~5,2%%date:~8,2%%time:~0,2%%time:~3,2%%time:~6,2%.txt" --data-urlencode "keyword=1" "http://www.400537.com/code/callback/"
choice /t 5 /d y /n >nul
goto next
```

### 列出当前目录所有
```
dir *.* /b >dir.txt
```
### 列出当前目录及后台目录的所有文件
```
dir /s /b >files.txt
```
### 列出所有文件，包含子目录的
```
tree /f >tree.txt
```
