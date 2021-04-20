<template>
	<div id="app">
		<div v-if="isHi">
			<HelloWorld v-for="item in messages" :msg="item.msg" :yes="item.yes" />
		</div>
		<div v-else>
			<List v-for="item in messages" :msg="item.msg" :yes="item.yes"></List>
		</div>
		<input @input="change()"/>
		<h1>{{meee}}</h1>
		<button type="button" @click="change()">切换</button>
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
				isHi: false

			}
		},
		computed: {
			meee: function() {
				return Date.now()
			}
		},
		methods: {
			change: function() {
				return this.isHi = !this.isHi
				
			}
		}

	}
</script>

<style>
</style>
