<script>
import Series from "./Library.svelte"
import Form from "./AddSeries.svelte"
</script>

<main>
	<h1>welcome!</h1>
	<h2>Add new serie</h2>
	<Form />
	<h2>or check out this series: </h2>
	<Series />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 2340px;
		margin: 0 auto;
	}

	h1 {
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
	}
	h2 {
		text-transform: uppercase;
		font-size: 1em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>