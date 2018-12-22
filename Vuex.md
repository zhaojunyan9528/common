Vuex核心是store，包含应用中的状态，与单纯的全局对象有以下两点不同：
	
	vuex的状态存储是响应式的
	只能通过提交commit mutation改变状态 mutation是同步函数

State单一状态树，每个应用仅仅包含一个store实例

mapState辅助函数，可获取多个状态

mapActions辅助函数将methods映射为store.commit

Action类似于mutation不同在于：

	Action提交的是mutation，而不是直接改变状态
	Action可以包含任意异步操作

代理作用是拦截请求然后转发请求