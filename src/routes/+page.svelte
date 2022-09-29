<h1 class="text-3xl font-bold">ShowShow</h1>
<p class="mb-4">Convert your list to one SQL pattern.</p>
<div class="flex">
	<div class="mb-2">
		<div>Text List:</div>
		<textarea name="source" id="source" cols="30" rows="10" class="p-2 border-2 border-cyan-700" />
	</div>

	<div class="mb-2 mx-2 pt-6">
		<p>Column Name:</p>
		<div><input class="p-2 border-2 border-cyan-700" /></div>
		<p class="mb-2">Start and End, add:</p>
		<button
			class="px-4 py-2 border-2 border-cyan-700 hover:bg-cyan-700 text-cyan-700 hover:text-white">
			( )
		</button>
		<p class="my-2">Each row (based on the column name you typed), add:</p>
		<button
			class="px-2 py-2 border-2 border-cyan-700 hover:bg-cyan-700  text-cyan-700 hover:text-white">
			or
		</button>
		<button
			class="px-4 py-2 border-2 border-cyan-700 hover:bg-cyan-700  text-cyan-700 hover:text-white">
			like
		</button>
		<button
			class="px-4 py-2 border-2 border-cyan-700 hover:bg-cyan-700  text-cyan-700 hover:text-white">
			front %
		</button>
		<button
			class="px-4 py-2 border-2 border-cyan-700 hover:bg-cyan-700  text-cyan-700 hover:text-white">
			end %
		</button>
	</div>

	<div class="mb-2">
		<div>Result:</div>
		<textarea name="result" id="result" cols="30" rows="10" class="p-2 border-2 border-cyan-700" />
	</div>
</div>
