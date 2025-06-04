<script>
	let mg = $state(0);
	let g = $state(0);
	let kg = $state(0);
	let t = $state(0);

	function miligrama() {
		g = mg / 1000;
		kg = mg / 1000000;
		t = mg / 1000000000;
	}

	function grama() {
		mg = g * 1000;
		kg = g / 1000;
		t = g / 1000000;
	}

	function kilograma() {
		mg = kg * 1000000;
		g = kg * 1000;
		t = kg / 1000;
	}

	function tonelada() {
		mg = t * 1000000000;
		g = t * 1000000;
		kg = t * 1000;
	}
</script>

<div class="container">
	<h1 style="color: #F67828">CONVERSOR DE MASSA</h1>
	<p>Miligramas: <input type="number" bind:value={mg} onclick={miligrama} /></p>
	<p>Gramas: <input type="number" bind:value={g} onclick={grama} /></p>
	<p>Quilogramas: <input type="number" bind:value={kg} onclick={kilograma} /></p>
	<p>Toneladas: <input type="number" bind:value={t} onclick={tonelada} /></p>
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
