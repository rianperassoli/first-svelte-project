<script>
	let a = 1;
	let b = 2;
	let result = 0;

	function sum(value1, value2) {
		return Number(value1) + Number(value2);
	}
</script>

<main>
	<input type="number" bind:value={a} />
	<input type="number" bind:value={b} />

	<p>{sum(a, b)}</p>
</main>
