<div class = 'page'>
<h1>Padel DAW Games</h1>
<img class = 'imagen' src={'padellogo.jpg'} alt=''>
<p></p>
{#if players.length < 8}
<input bind:value={name}>

<button on:click={addjugador}>Añadir</button>
{/if}


<ul>
    {#each players as player}
        <li>{player}<button on:click={() => removejugador(player)}>REMOVE</button></li>
    {/each}    
</ul>
</div>




<script>
    let name = '';
    let players = ['Carlos', 'Hector','Gerard', 'Josep', 'Alejandro', 'Juan','Manolo'];
    function addjugador() {
        if (players.length < 8) {
            players.push(name);
            players = players;
            name = '';
        }
        
    }
    function removejugador(playerToRemove) {
        players = players.filter(player => player !== playerToRemove);
    }
</script>





<style>
    .page{
        display: grid;
        justify-content: center;
        background-color: blanchedalmond;
        background-image: -webkit-linear-gradient();
    }

    li {
        list-style-type:upper-roman;
        text-align: center;
        text-shadow: 5cm;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-style: oblique;
        padding: 0.6em;
        box-shadow: 3px 3px 3px brown;
    }
    
</style>