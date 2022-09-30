<script>
	export let name;
	export let disabled = false;

	export let text = '';
</script>

<textarea
	id={name}
	{name}
	cols="30"
	rows="10"
	class="resize-none p-2 border-2 border-cyan-700"
	{disabled}
	bind:value={text} />
