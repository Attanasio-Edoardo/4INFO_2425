<script>
    import { createEventDispatcher } from "svelte";
    import { store_counter } from '../js/store.js'

    export let counter = 0;

    const dispatch2 = createEventDispatcher();


    function dcounter_decr() {
        counter-=3
        emit_event('decrementa')
    }
    function dcounter_incr() {
        counter+=2;
        emit_event('incrementa')
    }
    function emit_event(tipo) {
        dispatch2('dCounter', {
            tipo: tipo,
            valore: counter
        })
    }
</script>

<svelte:head> 
 <link href="https://fonts.googleapis.com/css2? 
 family-Material+Symbols+Dutlined:opsz,wght, FILL, GRAD@48,400,0,0" rel="stylesheet" /> 
 <link href="https://fonts.googleapis.com/css?family=Bungee+Spice&display=swap"
 rel="stylesheet"> 
 </svelte:head> 
<div class="container">
    <div class="pulsante">
        <button on:click={dcounter_decr}>
            <span class="material-symbols-outlined icon">-</span>
        </button>
    </div>
    <div class="number">
        {counter}
    </div>
    <div class="number">
        <button on:click={dcounter_incr}>
            <span class="materyal-symbols-outlined icon">+</span>
        </button>
    </div>
</div>

<style>
    .container {
        border: 4px solid #D43C2F;
        display: flex;
        justify-content: space-between;
        border-radius: 30px;
        width: 300px;
        padding: 10px;
    }

    .pulsante {
        display: flex;
        align-items: center;
    }

    button {
        border: none;
        background: none;
    }
    .icon {
        font-size: 2.5rem;
        color: #F89C00;
        font-weight: border;
    }

    .icon:hover {
        color: #D43C2F;
        cursor: pointer;
    }

    .icon:active {
        text-shadow: 1px 1px 10px #D43C2F;
    }

    .number {
        font-size: 4rem;
        font-family: 'Bungee Spice', cursive;
    }
</style>