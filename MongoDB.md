MongoDB非关系数据库、键值对数据、文档型数据库、快速开发
存储的是各种各样的json

1.安装MongoDB（官网下载，版本号偶数稳定版，奇数开发版）

2.配置环境变量

	path中添加安装路径的bin文件夹 例E:\MongoDB\bin

3.在c盘根目录

	存储数据的目录：创建data目录-》创建db目录

4.打开cmd命令窗口

	输入mongod 启动mongdb服务器 等待连接
	32位电脑第一次启动时：mongod --storageEngine==mmapv1
	可以通过mongod --dbpath url(启动指定数据库路径)
	默认端口27017
	指定端口号mongod --dbpath url(启动指定数据库路径) --port 1234

5.再打开cmd窗口

	输入mongo  连接

6.数据库

	数据库的服务器（保存数据） mongod 启动服务器
	数据库的客户端（操作数据） mongo  启动客户端

7.将MongoDB设置为系统服务，自动后台启动
	
	c盘根目录data下创建log日志文件
	在安装路径bin上一级目录创建配置文件mongod.cfg
		systemLog:
			destination:file
			path: c:\data\log\mongod.log
		storage:
			dbPath: c:\data\db
	以管理员身份打开命令窗口
	执行如下命令：
		sc.exe create MongoDB binPath="\"E:\MongoDB\bin\mongod.exe\" --service --config=\"E:\MongoDB\mongod.cfg\"" DisplayName="MongoDB" start="auto"
