<script>
	let points = 0;

	let add = 1;

	let cost1 = 10;
	let cost2 = 100;

	let autoclick1 = 0;
	let autoclick2 = 0;
	let autoclick3 = 0;
	let multiply = 1;

	setInterval(() => {
		points += (1 * autoclick1 + 5 * autoclick2 + 10 * autoclick3) * multiply;
	}, 500);

	function plus() {
		points += add * multiply;
	}

	function mainAdd() {
		if (points >= cost1) {
			points -= cost1;
			add += 1;
		}
	}

	function addAutoclick1() {
		if (points >= cost2) {
			points -= cost2;
			autoclick1 += 1;
		}
	}
</script>

<div class="content">
	<h1>{points} points</h1>
	<div class="buttons">
		<div class="btnBox 1">
			<p>+1 button</p>
			<button on:click={mainAdd}>cost {cost1}</button>
		</div>
		<div class="btnBox 2">
			<p>+1 autoclick</p>
			<button on:click={addAutoclick1}>cost {cost2}</button>
		</div>
	</div>

	<button class="btnMain" on:click={plus}> +{add} </button>
</div>

<style>
	:global(body) {
		background-color: #212121;
	}

	h1 {
		color: white;
		font-size: 70px;
		font-family: Arial, Helvetica, sans-serif;
		text-align: center;
	}

	.buttons {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	button {
		margin: 20px;
		background-color: white;
		border-radius: 50px;
		height: 50px;
		font-weight: 600;
	}

	p {
		margin: 20px;
		margin-bottom: -10px;
		color: white;
		font-family: Arial, Helvetica, sans-serif;
	}

	.btnBox {
		display: flex;
		flex-direction: column;
	}

	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.btnMain {
		border-radius: 100px;
		width: 200px;
		height: 200px;
		font-size: 50px;
	}
</style>
