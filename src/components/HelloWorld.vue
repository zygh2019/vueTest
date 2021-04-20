<template>
	<div class="hello">
		<p>我是普通用户</p>
		<h1>{{ msg }}</h1>
		<h2>{{yes}}</h2>
		<button @click="get()">点击购买了{{count}}次</button>
	</div>
</template>

<script>
	export default {
		name: 'HelloWorld',
		props: {
			msg: String,
			yes: String
		},
		methods: {
			get: function() {
			//	this.msg = "hhhhhhhhh"
				this.$emit('get');
			}

		},
		data: () => {
			return {
				count: 0
			}
		}

	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	p {
		font-size: 0.625rem;
	}
</style>
