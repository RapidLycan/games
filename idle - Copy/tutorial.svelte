<script>
	let points = 0;

	function plus() {
		points += add * multiply;
	}
</script>

<h1>{points} points</h1>

<button class="btnMain" on:click={plus}> +1 </button>
