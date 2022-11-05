<script>
  import PlayerScore from './PlayerScore.svelte'

  let player1Component;
  let player2Component;

  function reset() {
    player1Component.reset();
    player2Component.reset();
  }
</script>

<main>
  <PlayerScore bind:this={player1Component} playername="Player 1"/>
  <PlayerScore bind:this={player2Component} playername="Player 2"/>
  <button on:click={reset} class="contrast outline">RESET</button>
</main>

<style>
 
</style>
