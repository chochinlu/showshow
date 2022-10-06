<script>
	import Button from '../components/Button.svelte'
	import TextList from '../components/TextList.svelte'
	import DisabledButton from '../components/DisabledButton.svelte'

	let columnName = ''
	let sourceValue = ''

	let quoteSelected = false
	let frontSymbolSelected = false
	let backSymbolSelected = false
	$: sourceItemList = sourceValue.split('\n').filter((s) => s.length !== 0)

	$: tempTargetValue = sourceItemList
		.map(
			(s, index) =>
				`${index !== 0 ? 'OR' : ''} ${columnName} LIKE '${frontSymbolSelected ? '%' : ''}${s}${
					backSymbolSelected ? '%' : ''
				}'`
		)
		.join('\n')

	$: targetValue = `${quoteSelected ? '(' : ''} ${tempTargetValue} ${quoteSelected ? ')' : ''}`
</script>

<h1 class="text-3xl font-bold">ShowShow</h1>
<p class="mb-4">Convert your list to one SQL pattern.</p>
<div class="flex flex-col md:flex-row">
	<div class="mb-2 border-2">
		<div>Text List:</div>
		<TextList name="source" bind:text={sourceValue} />
	</div>

	<div class="mb-2 mx-0 pt-0 border-2 md:mx-2 md:pt-6">
		<p>Column Name:</p>
		<div>
			<input
				class="p-2 border-2 border-cyan-700"
				bind:value={columnName}
				placeholder="which column" />
		</div>
		<p class="mb-2">Start and End, add:</p>
		<Button bind:selected={quoteSelected}>( )</Button>
		<p class="my-2">Each row (based on the column name you typed), add:</p>
		<DisabledButton>OR</DisabledButton>
		<DisabledButton>LIKE</DisabledButton>
		<Button bind:selected={frontSymbolSelected}>front %</Button>
		<Button bind:selected={backSymbolSelected}>end %</Button>
	</div>

	<div class="mb-2 border-2">
		<div>Result:</div>
		<TextList name="result" disabled={true} bind:text={targetValue} />
	</div>
</div>
