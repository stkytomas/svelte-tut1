<script>
	let name = "Tony Stark";
	let points = 100;
</script>

<main>
	<h1>{name}</h1>
	<h3>{points}</h3>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: purple;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	h3 {
		color: rgb(13, 197, 13);
		font-size: 2em;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>