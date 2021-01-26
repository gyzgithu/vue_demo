<template>
	<div class="about">
		<h1>This is an about page</h1>
		<h1>计数器</h1>
		<p>
			<button @click="reduce">-</button>
			<span>{{num}}</span>
			<button @click="add">+</button>
		</p>
		<p>{{normal() }}</p>
		<p>{{computed1 }}</p>
		
	</div>
</template>

<script>
	export default {
		data() {
			return {
				num: 0
			}
		},
		methods: {
			normal() {
				console.log('普通方法执行了');
				return "普通方法"
			},
			reduce() {
				this.num--;

			},

			add() {
				this.num++;

			},
		},
		computed: {
			computed1() {
				console.log('计算属性执行了');
				return "计算属性" + this.num
			},

		},
		watch: {
			num(newvalue, oldvalue) {
				console.log("监听到num变化了", newvalue, oldvalue)
			}
		}

	}
</script>
