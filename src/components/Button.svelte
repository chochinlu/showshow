<script>
	export let selected = false;
	$: moreStyle = selected
		? 'text-white bg-cyan-700'
		: 'hover:bg-cyan-700 text-cyan-700 hover:text-white';

	function toggleSelected() {
		selected = !selected;
	}
</script>

<button {selected} class="px-4 py-2 border-2 border-cyan-700 {moreStyle}" on:click={toggleSelected}>
	<slot />
</button>
