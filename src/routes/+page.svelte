<script>
	import Button from '../components/Button.svelte';
	import TextList from '../components/TextList.svelte';

	let sourceValue = '';
	$: targetValue = sourceValue
</script>

<h1 class="text-3xl font-bold">ShowShow</h1>
<p class="mb-4">Convert your list to one SQL pattern.</p>
<div class="flex">
	<div class="mb-2">
		<div>Text List:</div>
		<TextList name="source" bind:text={sourceValue} />
	</div>

	<div class="mb-2 mx-2 pt-6">
		<p>Column Name:</p>
		<div><input class="p-2 border-2 border-cyan-700" /></div>
		<p class="mb-2">Start and End, add:</p>
		<Button>( )</Button>
		<p class="my-2">Each row (based on the column name you typed), add:</p>
		<Button>or</Button>
		<Button>like</Button>
		<Button>front %</Button>
		<Button>end %</Button>
	</div>

	<div class="mb-2">
		<div>Result:</div>
		<TextList name="result" disabled={true} bind:text={targetValue} />
	</div>
</div>
