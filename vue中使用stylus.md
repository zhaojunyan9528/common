vue中使用stylus
1.安装stylus
	npm install stylus --save
	npm install stylus-loader --save
2.组件使用
	<style lang='stylus' rel='stylesheet/stylus'>
		
	</style>
3.使用变量，基础样式文件index.styl中，定义$bgColor = #00bcd4
	@import '/index.styl'
	.main
		background $bgColor
4.使stylus样式代码格式化时不会改变格式
	1、安装stylus supremacy
	2.文件-首选项-设置-工作区设置
	3.搜索
		//是否插入冒号
		stylusSupremacy.insertColons:false 
		//是否插入分号
		stylusSupremacy.insertSemicolons:false 
		//是否插入大括号
		stylusSupremacy.insertBaraces:false
		//两个选择器是否换行
		stylusSupremacy.insertNewLineAroundBlocks:false 