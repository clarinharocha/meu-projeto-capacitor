<script>
  import { dicionario } from '$lib/dicionario.js';
  import { page } from '$app/stores';
  import { onMount } from 'svelte';

  let termoSelecionado;

  $: palavraParam = $page.params.palavra;

  onMount(() => {
    termoSelecionado = dicionario.find(t => t.palavra === palavraParam);
  });
</script>

<div class="container my-5">
  {#if termoSelecionado}
    <h1 class="display-4 text-capitalize">{termoSelecionado.palavra}</h1>
    <hr />
    <ol class="list-group list-group-numbered">
      {#each termoSelecionado.definicoes as definicao}
        <li class="list-group-item">{definicao}</li>
      {/each}
    </ol>
  {:else}
    <div class="alert alert-warning" role="alert">
      Palavra não encontrada.
    </div>
  {/if}

  <div class="mt-4">
    <a href="/dicionario" class="btn btn-secondary">Voltar ao dicionário</a>
  </div>
</div>
