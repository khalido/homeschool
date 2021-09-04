<script>
	let num = 2;
	let num2 = 2;
	let nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12];

	function padnum(n, pad = 12, w = 'a') {
		return n.toString().padStart(pad);
	}
</script>

<h1 class="text-5xl text-purple-900">{num} Times Table</h1>
<p class="text-lg mb-4">the times table and nothing else. Enter a number and get your table.</p>

<div class="flex">
	<div class="w-1/3">
		<label for="num" class="text-2xl p-0.5">Number:</label><br />
		<input name="num" class="text-3xl border w-5/6 p-2 mt-2" bind:value={num} />
	</div>

	<div class="w-2/3">
		<ul class="p-2 text-2xl">
			{#each nums as n}
				<li class="odd:bg-blue-50 even:bg-yellow-50 py-2 px-14">
					{num.toLocaleString()} x {padnum(n)} =
					<span class="text-red-900 font-bold">{(num * n).toLocaleString()}</span>
				</li>
			{/each}
		</ul>
	</div>
</div>

