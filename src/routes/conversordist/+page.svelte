<script>
	let m = $state(0);
	let km = $state(0);
	let mm = $state(0);
	let cm = $state(0);

	function metros() {
		cm = m * 100;
		mm = m * 1000;
		km = m / 1000;
	}

	function centimetros() {
		m = cm / 100;
		mm = cm * 10;
		km = cm / 100000;
	}

	function milimetros() {
		m = mm / 1000;
		km = mm / 1000000;
		cm = mm / 10;
	}

	function quilometros() {
		m = km * 1000;
		cm = km * 100000;
		mm = km * 1000000;
	}
</script>

<div class="container">
	<h1 style="color: #5E4D85">CONVERSOR DE DISTÂNCIA</h1>
	<p>Milimetros: <input type="number" bind:value={mm} onclick={milimetros} /></p>
	<p>Centimetros: <input type="number" bind:value={cm} onclick={centimetros} /></p>
	<p>Metros: <input type="number" bind:value={m} onclick={metros} /></p>
	<p>Quilometros: <input type="number" bind:value={km} onclick={quilometros} /></p>
</div>
<div class="button-container">
	<a href="/">
		<button class="styled-button3">Voltar</button>
	</a>
</div>

<style>
	.container {
		background-color: rgb(241, 195, 229);
		border-radius: 10px;
		text-align: center;
		padding: 30px;
		max-width: 700px;
		width: 100%;
		margin-top: 10%;
		box-shadow: 0 4px 8px rgb(235, 132, 192);
		margin: 100px auto;
		font-family: serif;
	}
	.button-container {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.styled-button3 {
		width: 260px;
		max-width: 100%;
		padding: 16px;
		margin: 12px 0;
		font-size: 18px;
		color: white;
		background-color: #ff69b4;
		border: none;
		border-radius: 50px;
		box-shadow: 0 4px 10px rgb(235, 132, 192);
		cursor: pointer;
		transition:
			transform 0.2s,
			background-color 0.3s ease;
	}
</style>
