<script>
	let points = 0;

	let add = 1;

	let cost1 = 10;
	let cost2 = 100;
	let cost3 = 500;
	let cost4 = 2500;
	let cost5 = 10000;

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
			cost1 += 5;
			add += 1;
		}
	}

	function addAutoclick1() {
		if (points >= cost2) {
			points -= cost2;
			cost2 += 20;
			autoclick1 += 1;
		}
	}
	function addAutoclick2() {
		if (points >= cost3) {
			points -= cost3;
			cost3 += 100;
			autoclick2 += 1;
		}
	}
	function addAutoclick3() {
		if (points >= cost4) {
			points -= cost4;
			cost4 += 1000;
			autoclick3 += 1;
		}
	}

	function addMultiply() {
		if (points >= cost5) {
			points -= cost5;
			cost5 += 10000;
			multiply += 1;
		}
	}
</script>

<div class="content">
	<h1>{points} points</h1>
	<div class="buttons">
		<div class="btnBox 1">
			<p>+1 button</p>
			<button class={points > cost1 ? '' : 'grey'} on:click={mainAdd}>cost {cost1}</button>
		</div>
		<div class="btnBox 2">
			<p>+1 autoclick</p>
			<button class={points > cost2 ? '' : 'grey'} on:click={addAutoclick1}>cost {cost2}</button>
		</div>
		<div class="btnBox 3">
			<p>autoclick 5</p>
			<button class={points > cost3 ? '' : 'grey'} on:click={addAutoclick2}>cost {cost3}</button>
		</div>
		<div class="btnBox 4">
			<p>autoclick 10</p>
			<button class={points > cost4 ? '' : 'grey'} on:click={addAutoclick3}>cost {cost4}</button>
		</div>
		<div class="btnBox 5">
			<p>multiply * 2</p>
			<button class={points > cost5 ? '' : 'grey'} on:click={addMultiply}>cost {cost5}</button>
		</div>
	</div>

	<button class="btnMain" on:click={plus}> +{add} </button>

	<p>
		current equation: +({`(1 * ${autoclick1} + 5 * ${autoclick2} + 10 * ${autoclick3}) * ${multiply}`})
		two times a seconds
	</p>
</div>

<style>
	:global(body) {
		background-color: #212121;
	}

	h1 {
		color: cornflowerblue;
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
		background-color: cornflowerblue;
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

	.grey {
		background-color: #303030;
	}
</style>
