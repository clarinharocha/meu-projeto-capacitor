<script>
    import { dicionario } from '$lib/dicionario';
    import { goto } from '$app/navigation';

    let palavra = $state('');
    let filtradas = $state(dicionario);

    function buscar() {
        if (palavra == '') {
            filtradas = dicionario;
            return;
        }
        
        filtradas = [];
        for (const termo of dicionario) {
            if (termo.palavra.startsWith(palavra)) {
                filtradas.push(termo);
            }
        }    
    }

    function aleatorio() {
        const index = Math.floor(Math.random() * dicionario.length);
        palavra = dicionario[index].palavra;
        goto(`/dicionario/${palavra}`);
    } 
</script>

<div class="container my-5">
    <div class="row mb-3">
        <div class="col-md-8">
            <input 
                type="text" 
                class="form-control" 
                placeholder="Digite uma palavra" 
                on:input={buscar} 
                bind:value={palavra}
            />
        </div>
        <div class="col-md-4 d-grid">
            <button 
                type="button" 
                class="btn btn-success" 
                on:click={aleatorio}
            >
                Palavra aleatória
            </button>
        </div>
    </div>

    <div class="row">
        <div class="col">
            <ul class="list-group">
                {#each filtradas as termo}
                    <li class="list-group-item">
                        <a href={`/dicionario/${termo.palavra}`} class="text-decoration-none">
                            {termo?.palavra}
                        </a>
                    </li>
                {/each}
            </ul>
        </div>
    </div>
</div>
