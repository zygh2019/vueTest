<template>
	<div id="app">

		<HelloWorld v-for="item in messages" :msg="item.msg" :yes="item.yes" />
		<List  v-for="item in messages" :msg="item.msg" :yes="item.yes"></List>
		<input  />
		
	</div>
</template>

<script>
	import HelloWorld from './components/HelloWorld.vue'
import List from './components/List.vue'
	export default {
		name: 'app',
		components: {
			HelloWorld,List
		},
		data: () => {
			return {
				messages: [{
					msg: '张三',
					yes: 'hh'
				}, {
					msg: '张三1',
					yes: 'hh2'
				}]
			}
		}

	}
</script>

<style>
</style>
