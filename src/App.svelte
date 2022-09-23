<script>

	import { onMount } from 'svelte';

	let adSpace;
	let minAdWidth = 10;
	let minAdHeight = 10;

	let adSpaceWidth = 1000;
	let adSpaceHeight = 1000;

	let verticalBlocks = adSpaceHeight / minAdHeight;
	let horizontalBlocks = adSpaceWidth / minAdWidth;

	const rows = [
								1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33,
								34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66,
								67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100
							];
	const cols = [
								1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33,
								34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66,
								67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100
							];


	let coords = {
		x: '',
		y: '',
		selected: false
	};

	let more = [];

	function click() {
		coords.selected = true;
		console.log(coords.x, coords.y)
	}

	
	onMount(() => {

	});

	
</script>

<main>

	<div class="title-container">
		<h1 class="title">NFT WALL</h1>
	</div>
<button on:click={click}>Click</button>
	<div class="box-container">
		<div style="width: {adSpaceWidth}px; height: {adSpaceHeight}px" class="area">

			{#each rows as row}
				<div class="row" id={row}>
					{#each cols as col}
						<div bind:this={coords} on:click={() => coords = {x: row, y: col}} class="block" id={col}>
							{#if row == coords.x && col == coords.y && coords.selected}
								<div class="tiny">1</div>
							{/if}
						</div>
					{/each}
				</div>
			{/each}

		</div>
	</div>
</main>

<style>
	.title-container {
		width: 100%;
		height: 100%;
		text-align: center;
	}

	.box-container {
		padding-bottom: 200px;
		width: 100%;
		height: 100%;
	}

	.area {
		border: 2px solid black;
		margin: 0 auto;
	}

	.row {
		display: flex;
		height: 10px;
		margin: 0;
	}

	.block {
		display: flex;
		height: 10px;
		width: 10px;
		margin: 0;
		/*
		background-size: contain;
		background-image: url("image.jpg");
		*/
	}

	.block:hover {
		cursor: pointer;
		background-color: red;
	}

	.tiny {
		display: inline-flex;
		font-size: 5px;
		text-align: center;
		align-items: center;
		background-color: greenyellow;
		width: 100%;
		height: 100%;
	}
	
</style>