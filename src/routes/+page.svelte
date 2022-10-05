<script>
	import Button from '../components/Button.svelte';
	import TextList from '../components/TextList.svelte';

	let columnName = '';
	let sourceValue = '';

	let frontSymbolSelected = false;
	let backSymbolSelected = false;
	$: sourceItemList = sourceValue.split('\n').filter((s) => s.length !== 0);

	$: targetValue = sourceItemList
		.map(
			(s, index) =>
				`${index !== 0 ? 'OR' : ''}${columnName} LIKE '${frontSymbolSelected ? '%' : ''}${s}${
					backSymbolSelected ? '%' : ''
				}'`
		)
		.join('\n');
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
		<div>
			<input
				class="p-2 border-2 border-cyan-700"
				bind:value={columnName}
				placeholder="which column" />
		</div>
		<p class="mb-2">Start and End, add:</p>
		<Button>( )</Button>
		<p class="my-2">Each row (based on the column name you typed), add:</p>
		<Button selected={true}>or</Button>
		<Button selected={true}>like</Button>
		<Button bind:selected={frontSymbolSelected}>front %</Button>
		<Button bind:selected={backSymbolSelected}>end %</Button>
	</div>

	<div class="mb-2">
		<div>Result:</div>
		<TextList name="result" disabled={true} bind:text={targetValue} />
	</div>
</div>
