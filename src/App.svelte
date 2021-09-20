<script>
import Series from "./Library.svelte"
import Form from "./AddSeries.svelte"
</script>

<main>
	<h1>Hello, check out this series!</h1>
	<Form />
	<Series />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>