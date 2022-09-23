<script>
	import { onMount } from 'svelte';
  let adSpace;
  let minAdWidth = 10;
	let minAdHeight = 10;

	let adSpaceWidth = 1000;
	let adSpaceHeight = 1000;

	let verticalBlocks = adSpaceHeight / minAdHeight;
	let horizontalBlocks = adSpaceWidth / minAdWidth;

function table() {
    adSpace = '<table style="width: 1000px; max-height: 1000px; border-spacing:0; border-collapse: collapse;">';
    for(let i = 1; i <= verticalBlocks; i++) {
      adSpace += '<tr style="width: 10px; max-height: 10px; padding: 0px;">';
      for(let j = 1; j <= horizontalBlocks; j++) {
        adSpace += `<td style="min-width: 10px; height: 10px; font-size: 5px; padding: 0px; background-color: red;">${j}</td>`;
      }
      adSpace += '</tr>';
    }
    adSpace += '</table>';
    console.log(adSpace)

    return adSpace;
  }

  onMount(() => {
		table()
	});


</script>

<div class="table-container">{@html adSpace}</div>