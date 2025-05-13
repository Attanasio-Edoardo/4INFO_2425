<script>
    let nome, cognome, eta, residenza;
    let confermato = true;
</script>

<h1>Input Page</h1>

Nome <input bind:value={nome}>
cognome <input bind:value={cognome}>
Eta<input bind:value={eta}>
Residenza <input bind:value={residenza}>
<br><br>
Confermato <input type="checkbox" bind:checked={confermato}>
<br><br>
Io sono {nome} {cognome} e ho {eta} anni
<br><br>

<button disabled={!confermato}>Invia</button>