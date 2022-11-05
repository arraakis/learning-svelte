<script>
    export let playername;
    let playerScore = 0;

    function increasePlayerScore() {
        playerScore += 1;
    }

    function decreasePlayerScore() {
        playerScore -= 1;
        if (playerScore < 0) {
            playerScore = 0;
        }
    }

    export function reset() {
        playerScore = 0;
    }





</script>

<div>
    <h2 class="center">{playername}</h2>
    <h3 class="center">{playerScore}</h3>
    <button on:click={increasePlayerScore}>Increase</button>
    <button on:click={decreasePlayerScore}>Decrease</button>
</div>

<style>
    .center {
        text-align: center;
    }
</style>