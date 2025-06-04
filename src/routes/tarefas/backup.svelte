<script>
	const tarefas = $state([
		'lavar a louça',
		'arrumar o quarto',
		'comprar chocolate pro amigo secreto'
	]);
	let novaTarefa = $state();
	let indiceTarefa = $state();
	let itemTarefa = $state();

	function adicionarTarefa() {
		tarefas.push(novaTarefa);
		novaTarefa = '';
	}
	function excluirTarefa(i) {
		tarefas.splice(i, 1);
	}
	function editarTarefa(i) {
		indiceTarefa = i;
		itemTarefa = tarefas[i];
	}
	function salvarTarefa(i) {
		tarefas[i] = itemtarefa;
		indiceTarefa = null;
	}
	function cancelarEdicao(i) {
		indiceTarefa = -1;
		itemTarefa = '';
	}
</script>

<div class="container">
	<h2 style="color: #FF007F">Lista de tarefas</h2>
	<p>
		<input placeholder="digite a tarefa..." bind:value={novaTarefa} />
		<button onclick={adicionarTarefa}>+</button>
	</p>
	<ul>
		{#each tarefas as tarefa, i}
			<li>
				{#if indiceTarefa == i}
					<input bind:value={itemTarefa} />
					<button onclick={() => salvarTarefa(i)}>s</button>
					<button onclick={() => cancelarEdicao(i)}>c</button>
				{:else}
					{tarefa}
					<button onclick={() => editarTarefa(i)}>e</button>
					<button onclick={() => excluirTarefa(i)}>-</button>
				{/if}
			</li>
		{/each}
	</ul>
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
