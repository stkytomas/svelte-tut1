<script>
//const { }=require("node:os");

	let name = "Tony Stark";
	let points = 100;

const addPoint = () => points += 1;
const removePoint = () => points -= 1;
</script>

<main>
	<div class="container">
		<div class="card">
			<h1>{name}</h1>
			<h3>{points}</h3>
			<button class="btn" on:click={addPoint}>+1</button>
			<button class="btn btn-2" on:click={removePoint}>-1</button>
			<input type="number" bind:value={points} />
		</div>
	</div>	
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
		color: rgb(2, 26, 245);
		font-size: 2em;
		margin-bottom: 10px;
	}

	.btn {
		color:rgb(4, 211, 93);
	}

	.btn-2 {
		color: red;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>