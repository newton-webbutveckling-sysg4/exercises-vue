<template>
	<div class="hello">
		<h1> Övningar </h1>
		<section>
			<h2> Övning 2 </h2>
			Värde: {{ counter }}
			<button v-on:click="increaseCounter"> Öka värde </button>
			<button v-on:click="decreaseCounter"> Minska värdet </button>
			<button v-on:click="resetCounter"> Återställ </button>
		</section>
	</div>
</template>

<script>
export default {
	name: 'HelloWorld',
	data: () => ({
		counter: 10
	}), // data
	methods: {
		increaseCounter() {
			this.counter += 1
		},
		decreaseCounter() {
			this.counter -= 1
		},
		resetCounter() {
			this.counter = 10
		}
	} // methods
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section {
	border: 1px solid gray;
	margin: 1em;
	padding: 1em;
}
button {
	margin-left: 1em;
	margin-right: 1em;
}

</style>
