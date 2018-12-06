1、node安装   node -v检查是否安装node
2.vue-cli 全局安装 
	命令行：npm install -g vue-cli
3.初始化项目
	命令行：npm init webpack yourProjectname
	进入项目yourProjectname: cd yourProjectname
	安装vue：npm install
4.运行项目
	命令行：npm run dev
	运行：http://localhost:8080
5.打包项目
	命令行：npm run build
	打包后运行dist需要安装serve:npm install -g serve
	serve dist
	访问：http://localhost:5000