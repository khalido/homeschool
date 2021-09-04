<script>
	import { fade, fly } from 'svelte/transition';
	import { tweened } from 'svelte/motion';
	
	export let maxnum = 1000;
	let num = 1;

	function padnum(n, pad = 12, w = 'a') {
		return n.toString().padStart(pad);
	}

	function changeNum(max = maxnum) {
		num = Math.floor(Math.random() * max);
	}

	function handleOdd() {
		

		changeNum();
	}
	function handleEven() {
		if (num % 2 == 0) alert('you got it right');
		else alert("wrong wrong wrong");

		changeNum();
	}
</script>

<h1 class="text-5xl text-purple-900">Odd Even</h1>
<p class="text-lg mb-4">the times table and nothing else. Enter a number and get your table.</p>

<div class="w-full flex z-0 justify-center items-center">
	<button
		on:click={handleOdd}
		class="w-1/2 z-10 relative bg-yellow-200 hover:bg-red-800 h-screen"
	/>

	<button on:click={handleEven} class="w-1/2 relative z-10 bg-blue-200 h-screen" />

	<div class="z-50 absolute border border-red-400 p-4 items-center align-middle justify-center" >
		<p class="text-6xl" transition:fade>{num}</p>
	</div>
</div>
