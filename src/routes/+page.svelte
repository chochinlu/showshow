<h1 class="text-3xl font-bold">ShowShow</h1>
<p class="mb-2">Convert your list to one SQL pattern.</p>
<div class="mb-2">
	<div>Column Name:</div>
	<div><input class="p-2 border-2 border-cyan-700" /></div>
</div>
<div class="mb-2">
	<div>Text List:</div>
	<textarea name="source" id="source" cols="30" rows="10" class="p-2 border-2 border-cyan-700" />
</div>

<div>
	<p class="mb-2">Start and End, add:</p>
	<button
		class="px-4 py-2 border-2 border-cyan-700 hover:bg-cyan-700 text-cyan-700 hover:text-white">
		( )
	</button>
	<p class="my-2">Each row (based on the column name you typed), add:</p>
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
