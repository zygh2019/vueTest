<template>
	<div id="app">
		<div v-if="isHi">
			<HelloWorld v-for="item in messages" :msg="item.msg" :yes="item.yes" />
		</div>
		<div v-else>
			<List v-for="item in messages" :msg="item.msg" :yes="item.yes"></List>
		</div>
		<input @input="change()" v-model="inputData" />
		<h1>{{meee}}</h1>
		<h1>{{meee1}}</h1>
		<h1>{{count}}</h1>
		<button type="button" @click="change()">切换</button>
		<button type="button" @click="init()">count+1</button>
	</div>

</template>

<script>
	import HelloWorld from './components/HelloWorld.vue'
	import List from './components/List.vue'
	export default {
		name: 'app',
		components: {
			HelloWorld,
			List
		},
		data: () => {
			return {
				messages: [{
					msg: '张三',
					yes: 'hh'
				}, {
					msg: '张三1',
					yes: 'hh2'
				}],
				isHi: false,
				inputData: '初始值',
				count: 0

			}
		},
		computed: {
			meee: function() {
				return Date.now()
			},
			meee1: {
				get: function() {
					//我自己的值
					return this.meee1 = this.inputData
				},
				set: function() {
					//	我发生变化后修改的值
					this.count = ++this.count
				}
			}
		},
		/**如果一个数据需要经过复杂计算就用 computed在这个示例中，
		使用 watch 选项允许我们执行异步操作 (访问一个 API)，
		限制我们执行该操作的频率，并在我们得到最终结果前，设置中间状态。
		这些都是计算属性无法做到的。**/
		watch: {
			meee1: () => {
				alert("我是通过watch得到的")
			}
		},
		methods: {
			change: function() {
				return this.isHi = !this.isHi

			},
			init: function() {
				this.meee1 = "234"
			}
		}

	}
</script>

<style>
</style>
