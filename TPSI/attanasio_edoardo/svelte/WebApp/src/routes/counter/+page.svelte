<script>
    import Counter from "$lib/components/counter.svelte";
    import DoubleCounter from "$lib/components/doubleCounter.svelte";
    
    let contatore = 0;
    let dCounter = 0;
    let numeri = [1,26,63,24,15]
    let sottolineato = true

    $:sottolineato = dCounter % 2 == 0 ? true : false;
    $:doppio = contatore*2;

    function gestisci_evento(evento) {
        alert(`${evento.detail.tipo} -- ${evento.detail.valore}`);
    }
</script>

<h1>Pagina counter</h1>
{#if contatore < 5}
    <h2 class="rosso" class:sottolineato>Il valore del contatore vale: {contatore}</h2>
{:else}
    <h2 class="verde">Il valore del contatore vale: {contatore}</h2>
{/if}
<h2>Il suo doppio vale: {doppio}</h2>
<br><br>
<Counter bind:counter={contatore} on:contatore={gestisci_evento}/>
<br><br>
<h2 class={dCounter < 5 ? "" : "rosso"} class:sottolineato>Il valore double counter: {dCounter}</h2>
<br><br>
<DoubleCounter bind:counter={dCounter} on:dCounter={gestisci_evento}/>

<ul>
    {#each numeri as numero, indice}
        <li>numeri[{indice}]: {numero}</li>
    {/each}
</ul>

<style>
    .rosso {color: red;}
    .verde {color: green;}
    .sottolineato {text-decoration: underline;}
</style>