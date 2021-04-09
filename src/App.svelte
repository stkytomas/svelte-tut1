<script>
//const { }=require("node:os");
import Navbar from "./Navbar.svelte";
import Player from "./Player.svelte";
import AddPlayer from "./AddPlayer.svelte";

let players = [
	{
		name: "Tony Stark",
		points: 53
	},
	{
		name: "Wanda Maximoff",
		points: 101
	},
	{
		name: "Wade Wilson",
		points: 345678
	},
	{
		name: "Peter Parker",
		points: 51
	}
];

const addPlayer = e => { //`(e)` takes in event parameter
	const newPlayer = e.detail;
	players = [...players, newPlayer]; //spreads across current players arr and adds new player
};

// 	let name = "Tony Stark";
// 	let points = 100;
// 	let showControls = false;

// const addPoint = () => points += 1;
// const removePoint = () => points -= 1;
// const toggleControls = () => (showControls = !showControls);
</script>

<Navbar />
	<div class="container">
		<AddPlayer on:addplayer={addPlayer} />
		{#if players.length === 0}
			<p>NO PLAYERS!</p>
		{:else}
			{#each players as player}
				<Player 
				name={player.name} 
				points={player.points}
				/>
			{/each}
		{/if}
		<!-- <div class="card">
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
		</div> -->
	</div>	

<!-- <style>
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
</style> -->