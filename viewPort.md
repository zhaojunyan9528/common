列出所有端口：

	netstat -ano

查看被占用端口:

	netstat -ano|findstr "8080"

查看占用端口的进程：

	tasklist|findstr "8080"

结束进程：

	taskkill /f /t /im xxx.exe