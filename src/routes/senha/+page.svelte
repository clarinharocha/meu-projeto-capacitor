<script>
    let n = 1;
    let numeroAleatorio1 = "";
    let numeroAleatorio2 = "";
    let numeroAleatorio3 = "";
    let mensagem = "";
    let incluirMinusculas = false;
    let incluirMaiusculas = false;
    let incluirSimbolos = false;
    let incluirNumeros = true;

    function gerarNumeroAleatorio() {
        let caracteres = "";
        if (incluirNumeros) {
            caracteres += "0123456789";
        }
        if (incluirMinusculas) {
            caracteres += "abcdefghijklmnopqrstuvwxyz";
        }
        if (incluirMaiusculas) {
            caracteres += "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        }
        if (incluirSimbolos) {
            caracteres += "!@#$%^&*()_+-=[]{}|;:,.<>?";
        }

        if (caracteres === "") {
            mensagem = "Selecione pelo menos uma opção!";
            return;
        }

        numeroAleatorio1 = gerarSenha(caracteres);
        numeroAleatorio2 = gerarSenha(caracteres);
        numeroAleatorio3 = gerarSenha(caracteres);

        mensagem = "Senhas geradas com sucesso!";
    }

    function gerarSenha(caracteres) {
        let senha = "";
        for (let i = 0; i < n; i++) {
            senha += caracteres.charAt(Math.floor(Math.random() * caracteres.length));
        }
        return senha;
    }

    function copiarSenha(senha) {
        navigator.clipboard.writeText(senha)
            .then(() => {
                mensagem = "Senha copiada para a área de transferência!";
            })
            .catch(() => {
                mensagem = "Erro ao copiar a senha.";
            });
    }
</script>

<style>
    .container {
        background-color: beige;
       border-radius: 10px;
       text-align: center;
       padding: 30px;
       max-width: 700px;
       width: 100%;
       margin-top: 10%;
       box-shadow: 0 4px 8px palevioletred;
       margin: 100px auto;
    }

    h2 {
        color: #ff07c1;
    }

    button {
        margin-top: 10px;
    }

    p {
        font-size: 1.1em;
    }

    .message {
        margin-top: 10px;
        font-weight: bold;
        color: #ff07c1; 
    }
    .error-message {
        margin-top: 10px;
        font-weight: bold;
        color: #ff07c1; 
    }

    input[type="range"] {
        width: 80%;
        margin: 20px 0;
        color: #ff07c1;
    }

    .checkbox-group {
        text-align: left;
        margin: 15px 0;
    }

    .checkbox-group label {
        display: block;
        margin: 5px 0;
    }

    .checkbox1 {
        accent-color: #ff07c1;
    }
</style>

<div class="container">
    <h2>GERADOR DE SENHA</h2>
    <p>ESCOLHA A QUANTIDADE DE CARACTERES PARA A SENHA:</p>
    
    <input type="range" min="1" max="30" bind:value={n} style="accent-color: #ff07c1;"/>
    <p><strong>{n}</strong> CARACTERES</p>
    
    <div class="checkbox-group">
        <label><input type="checkbox" bind:checked={incluirNumeros} class="checkbox1"/> INCLUIR NÚMEROS</label>
        <label><input type="checkbox" bind:checked={incluirMinusculas} class="checkbox1"/> INCLUIR LETRAS MINÚSCULAS</label>
        <label><input type="checkbox" bind:checked={incluirMaiusculas} class="checkbox1"/> INCLUIR LETRAS MAIÚSCULAS</label>
        <label><input type="checkbox" bind:checked={incluirSimbolos} class="checkbox1"/> INCLUIR SÍMBOLOS</label>
    </div>

    <button type="button" class="btn btn-danger" on:click={gerarNumeroAleatorio}>GERAR SENHAS</button>

    {#if numeroAleatorio1 && numeroAleatorio2 && numeroAleatorio3}
        <p><strong>SENHA 1:</strong> {numeroAleatorio1}</p>
        <button type="button" class="btn btn-danger" on:click={() => copiarSenha(numeroAleatorio1)}>COPIAR SENHA 1</button>
        
        <p><strong>SENHA 2:</strong> {numeroAleatorio2}</p>
        <button type="button" class="btn btn-danger" on:click={() => copiarSenha(numeroAleatorio2)}>COPIAR SENHA 2</button>
        
        <p><strong>SENHA 3:</strong> {numeroAleatorio3}</p>
        <button type="button" class="btn btn-danger" on:click={() => copiarSenha(numeroAleatorio3)}>COPIAR SENHA 3</button>
    {/if}

    {#if mensagem}
        <p class={numeroAleatorio1 || numeroAleatorio2 || numeroAleatorio3 ? 'message' : 'error-message'}>{mensagem}</p>
    {/if}
</div>