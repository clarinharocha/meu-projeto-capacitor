<script>
    let n = 60;
    let quantidade = 6;
    let sorteados = []

    function sortear() {
        sorteados = [];
        for (let j = 0; j < quantidade; j++) {
            let numero = Math.trunc(Math.random() * n)
            sorteados.push(numero);
        }
    }
</script>
<div class="container text-center mt-5">
    <h1>Mega Sena</h1>
    <br />
    <button class="btn btn-secondary" onclick={sortear}>Sortear Número</button>
    <br />
    <br />
    <hr />
    <p><b>Os números sorteados são:</b></p>
    <h2>{sorteados}</h2>
</div>