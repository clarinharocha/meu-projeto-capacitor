<script>
	let celsius = $state(0);
	let kelvin = $state(0);
	let fahrenheit = $state(0);

	function Celsius() {
		fahrenheit = celsius * 1.8 + 32;
		kelvin = celsius + 273;
	}

	function Fahrenheit() {
		celsius = ((fahrenheit - 32) * 5) / 9;
		kelvin = ((fahrenheit - 32) * 5) / 9 + 273;
	}

	function Kelvin() {
		celsius = kelvin - 273;
		fahrenheit = ((kelvin - 273) * 1, 8) + 32;
	}
</script>

<div class="container">
	<h1 style="color: #007FFF">CONVERSOR DE TEMPERATURA</h1>
	<p>Celsius: <input type="number" bind:value={celsius} onclick={Celsius} /></p>
	<p>Fahrenheit: <input type="number" bind:value={fahrenheit} onclick={Fahrenheit} /></p>
	<p>Kelvin: <input type="number" bind:value={kelvin} onclick={Kelvin} /></p>
</div>
<div class="button-container">
	<a href="/">
		<button class="styled-button3">voltar</button>
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
