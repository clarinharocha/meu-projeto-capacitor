<script>
    let display = '';

    function press(c) {
        display += c;
    }

    function calc() {
        try {
            display = eval(display);
        } catch (e) {
            display = 'Erro';
        }
    }

    function clear() {
        display = '';
    }

    function invertSignal() {
        try {
            display = eval(display) * -1;
        } catch (e) {
            display = 'Erro';
        }
    }

    function square() {
        try {
            const val = eval(display);
            display = val * val;
        } catch (e) {
            display = 'Erro';
        }
    }

    function sqrt() {
        try {
            const val = eval(display);
            display = Math.sqrt(val);
        } catch (e) {
            display = 'Erro';
        }
    }

    function round() {
        try {
            const val = eval(display);
            display = Math.round(val);
        } catch (e) {
            display = 'Erro';
        }
    }

    function log10() {
        try {
            const val = eval(display);
            display = Math.log10(val);
        } catch (e) {
            display = 'Erro';
        }
    }
</script>

<div class="text-center mt-3">
    <input class="form-control" readonly bind:value={display}/>
    <table class="table table-sm table-borderless">
        <tbody>
            <tr>
                <td><button type="button" class="btn btn-secondary w-100" onclick={() => clear()}>C</button></td>
                <td><button type="button" class="btn btn-secondary w-100" onclick={round}>Arred</button></td>
                <td><button type="button" class="btn btn-secondary w-100" onclick={log10}>log₁₀</button></td>
                <td><button type="button" class="btn btn-warning w-100" onclick={() => press('%')}>%</button></td>
                <td><button type="button" class="btn btn-warning w-100" onclick={sqrt}>√x</button></td>
            </tr>

            <tr>
                <td><button type="button" class="btn btn-secondary w-100" onclick={invertSignal}>±</button></td>
                <td><button type="button" class="btn btn-secondary w-100" onclick={() => press('(')}>(</button></td>
                <td><button type="button" class="btn btn-secondary w-100" onclick={() => press(')')}>)</button></td>
                <td><button type="button" class="btn btn-warning w-100" onclick={() => press('/')}>/</button></td>
                <td><button type="button" class="btn btn-warning w-100" onclick={square}>x²</button></td>
            </tr>
            <tr>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(7)}>7</button></td>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(8)}>8</button></td>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(9)}>9</button></td>
                <td><button type="button" class="btn btn-warning w-100" onclick={() => press('*')}>X</button></td>
            </tr>
            <tr>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(4)}>4</button></td>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(5)}>5</button></td>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(6)}>6</button></td>
                <td><button type="button" class="btn btn-warning w-100" onclick={() => press('-')}>-</button></td>
            </tr>
            <tr>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(1)}>1</button></td>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(2)}>2</button></td>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(3)}>3</button></td>
                <td rowspan="2" style="height: 0px">
                    <button type="button" class="btn btn-warning w-100 h-100" onclick={() => press('+')}>+</button>
                </td>
            </tr>
            <tr>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press(0)}>0</button></td>
                <td><button type="button" class="btn btn-dark w-100" onclick={() => press('.')}>.</button></td>
                <td><button type="button" class="btn btn-warning w-100" onclick={() => calc()}>=</button></td>
            </tr>
        </tbody>
    </table>
</div>
