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

		<section>
			<h2> Övning 3 </h2>
			<button v-on:click="toggleText"> {{ textIsVisible ? 'Göm' : 'Visa' }} texten </button>
			<span v-show="textIsVisible"> Now you see me </span>
			<span v-show="!textIsVisible"> Now you don't </span>
		</section>

		<section>
			<h2> Övning 5</h2>
			<div class="carousel">
				<button v-on:click="previousImage"
					v-bind:disabled="currentIndex == 0"> &lt; </button>
				<img v-bind:src="images[currentIndex]" />
				<button v-on:click="nextImage"
					v-bind:disabled="currentIndex == images.length - 1"> &gt; </button>
			</div>
		</section>
	</div>
</template>

<script>
export default {
	name: 'HelloWorld',
	data: () => ({
		textIsVisible: true,
		counter: 10,
		currentIndex: 0,
		images: [
			'https://careofnature.se/wp-content/uploads/2020/04/Care-of-Nature-Ray-of-Light-1080x600-1.jpg',
			'https://imgproxy.natucate.com/PAd5WVIh-tjEKQM4Z6tm6W1J4Yc2JIYWrKEroD1c7mM/rs:fill/g:ce/w:3840/h:2160/aHR0cHM6Ly93d3cubmF0dWNhdGUuY29tL21lZGlhL3BhZ2VzL3JlaXNlYXJ0ZW4vNmMwODZlYmEtNzk3Yi00ZDVjLTk2YTItODhhNGM4OWUyODdlLzM3NjYwMTQ2NjMtMTU2NzQzMzYxMi8xMl9kYW5pZWxfY2FuX2JjLTIwNy5qcGc',
			'https://images.theconversation.com/files/399816/original/file-20210510-5797-xqoxsr.jpg?ixlib=rb-1.1.0&q=45&auto=format&w=1200&h=1200.0&fit=crop'
		]
	}), // data
	methods: {
		toggleText() {
			this.textIsVisible = !this.textIsVisible
		},
		increaseCounter() {
			this.counter += 1
		},
		decreaseCounter() {
			this.counter -= 1
		},
		resetCounter() {
			this.counter = 10
		},
		previousImage() {
			this.currentIndex -= 1
		},
		nextImage() {
			this.currentIndex += 1
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
h1, h2 {
	margin: 0em;
}
.carousel {
	display: flex;
	flex-direction: row;
	width: 12em;
	border: 1px solid black;
}
.carousel img {
	flex-grow: 1;
	height: 10em;
}
.carousel button {
	margin: 0em;
	border: none;
}

</style>
