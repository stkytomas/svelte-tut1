<script>
//const { }=require("node:os");
import Navbar from "./Navbar.svelte";
	let name = "Tony Stark";
	let points = 100;
	let showControls = false;

const addPoint = () => points += 1;
const removePoint = () => points -= 1;
const toggleControls = () => (showControls = !showControls);
</script>

<Navbar />
	<div class="container">
		<div class="card">
			<h1>
				{name}
				<button class="btn btn-sm" on:click={toggleControls}>
				{#if showControls}-{:else}+{/if}
				</button>
			</h1>
			<h3>Current Points: {points}</h3>
			{#if showControls}
				<button class="btn" on:click={addPoint}>+1</button>
				<button class="btn btn-2" on:click={removePoint}>-1</button>
				<input type="number" bind:value={points} />
			{/if}
		</div>
	</div>	

<style>
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