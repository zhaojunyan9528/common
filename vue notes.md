#vue渐进式JavaScript框架

核心库和插件，核心库很小，需要其他插件时添加进来

核心库只关注视图层，动态构建用户界面

框架顺序：angluar(数据绑定和模板)、react（组件化和虚拟Dom技术）、vue

1、vue的特点
	
	遵循MVVM模式
	编码简洁、体积小、运行效率高
	本身只关注UI，可以轻松引入插件（依赖vue)或第三方库(不依赖vue)开发项目

2、vue借鉴  

		angluar(数据绑定和模板)
		react（组件化和虚拟Dom技术）

3、vue扩展插件

	vue-cli:vue脚手架
	vue-resources(axios):ajax请求
	vue-router:路由
	vue-scroll:页面滑动
	vue-lazyload：图片懒加载
	vuex:状态管理模式
	mint-ui：基于vue的UI组件库（移动端）
	element-UI：基于vue的UI组件库（pc端）

4、vue的使用

	1.引入vue.js
	2.创建vue实例,el指定选择器范围，data初始化数据
	new vue({
		el:'app',
		data:{
			message:'hello'		
		}
	})

5.MVVM

	model:模型、数据对象（data）
	view:视图、模板页面（指令、{{}}显示数据）
	viewmodel:视图模型（vue的实例）
				      viewmodel
	view-------------dom listener-------------->model
	view<------------data bindings--------------model
	(DOM)              (vue实例)              (js objects)

6、数据绑定：Mustache语法（双大括号）{{msg}}

7、v-once一次性的插值，当数据改变时，内容不会更新

8、v-html输入真正的HTML

9、v-bind：href将mustache语法作用于HTML特性上可简写：href

10、使用JavaScript表达式{{msg.toUpperCase()}}

11、指令：带有v-前缀的特殊特性  v-if  v-for

12、v-on:click简写为：@click

13、计算属性computed和侦听属性watch
	
	computed的set监听方法，值改变时调用set回调方法，需要显示值时，调用get回调方法
	计算属性存在缓存，多次读取只执行一次getter计算

14、class和style绑定

	:class="classA"(字符串）
	:class="{classA:isA,classB:isB}"(对象)
	:class="['classA;,'classB']"(数组）
	:style="{color:activeColor,fontSize:fontSize+'px'}"(样式JS写法）

15、条件渲染

	v-if v-else-if v-else v-show
	v-if是惰性的如果初始条件为假则什么都不做，直到条件第一次变为真时，v-show不管初始条件真假，元素总被渲染，并且知识简单地基于css切换
	v-if有更高的切换开销，v-show有更高的初始渲染开销，因此，需频繁切换则使用v-show较好，如果运行时条件很少改变，则使用v-if
	
16、不建议v-if和v-show同时使用，v-for具有比v-if更高的优先级

17、列表渲染

	v-for="item in items"/v-for="(item,index) in items"
	可用of代替in
	遍历对象按Object.keys()结果遍历

18、数组更新检测-变异方法
	
	vue包含一组观察数组的变异方法，也会触发视图更新：
	push()向数组末尾添加一个或多个元素，返回新的长度
	pop()删除并返回数组的最后一个元素
	shift()删除数组第一个元素并返回第一个元素的值
	unshift()向数组开头添加一个或更多元素，并返回新的长度
	splice()增、删、改数组项目，返回被删除的项目，改变原数组
	sort()数组排序
	reverse()颠倒数组的元素顺序，会改变原数组

19、filter数组过滤 sort排序

20、绑定事件@click='test($event)',$event代表当前绑定事件标签

	test(event){ var text = event.target.innerHTML}

21、事件冒泡：从子到父依次执行，阻止事件冒泡，事件修饰符@click.stop="test"原生写法:event.stopPropagation()

22、阻止事件的默认行为(比如跳转），@click.prevent="test"原生写法：event.preventDefault

23、按键修饰符@click.enter .tab .deleter .esc .space .up .down .left .right

24、使用v-model对表单数据自动收集 双向绑定

26、vue实例的生命周期

	new vue 创建vue实例
	初始化显示（执行一次）：
	beforeCreate
		初始化设置：observe data  init events
	created
	beforeMount
	mounted
	更新状态（执行n次）：
	beforeUpdate
	updated
	销毁vue实例（执行n次）：
	beforeDestory
	destroyed
	
	常用生命周期：
	mounted：请求ajax请求，设置定时器等
	beforeDestroyed:销毁vue实例前，清除定时器等

27、transition过渡动画

	在目标元素外包裹<transition name="xxx"></transition>
	定义class样式：
		xxx-enter-active   xxx-leave-active
		xxx-enter          xxx-leave-to

28、自定义过滤器

	1.在组件的选项中定义本地过滤器
	2.在创建vue实例前定义全局过滤器
	页面使用：
	{{date | filterDate('YYYY-MM-DD')}}
	js:
	引入：import format from 'date-fns/format'
	filters:{
		filterDate:function(value,fmt){
			return format(value,fmt || 'YYYY-MM-DD HH:mm:ss')
		}	
	}
	
29、指令

	v-text:更新元素的textContext
	v-html:更新元素的innerHTML
	v-show:条件为true，切换元素的display属性
	v-if
	v-else-if
	v-else
	v-for:列表渲染
	v-on/@:绑定事件监听器
	v-bind:简写：，绑定Dom属性
	v-model:在表单控件上双向绑定
	v-pre:跳过这个元素和它的子元素的编译过程
	v-cloak:<div v-cloak>{{ message }}</div>这个指令保持在元素上直到关联实例结束编译
	v-once:只渲染元素和组件一次
	
	
	



