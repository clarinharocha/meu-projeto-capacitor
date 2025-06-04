<script>
	let s = $state(0);
	let min = $state(0);
	let h = $state(0);

	function segundos() {
		min = s / 60;
		h = s / 3600;
	}

	function minutos() {
		s = min * 60;
		h = min / 60;
	}

	function horas() {
		s = h * 3600;
		min = h * 60;
	}
</script>

<div class="container">
	<h1 style="color: #FF69B4">CONVERSOR DE TEMPO</h1>
	<p>Segundos: <input type="number" bind:value={s} onclick={segundos} /></p>
	<p>Minutos: <input type="number" bind:value={min} onclick={minutos} /></p>
	<p>Horas: <input type="number" bind:value={h} onclick={horas} /></p>
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
