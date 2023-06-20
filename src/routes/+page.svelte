<script>
  import Header from "$lib/Header.svelte";
  import Footer from "$lib/Footer.svelte";
  let userMove = "";
  let autoMove = "";
  let response = "";
  let buttonsVisible = true;

  function paper() {
    userMove = "paper";
    buttonsVisible = false;
    let index = Math.floor(Math.random(0) * autoMoves.length);
    autoMove = autoMoves[index];
    if (autoMove == "paper") {
      response = "tie";
    } else if (autoMove == "rock") {
      response = "win";
    } else {
      response = "lose";
    }
    userMove = paper.png;
  }
  function scissors() {
    buttonsVisible = false;
    userMove = "scissors";
    let index = Math.floor(Math.random(0) * autoMoves.length);
    autoMove = autoMoves[index];
    if (autoMove == "scissors") {
      response = "tie";
    } else if (autoMove == "paper") {
      response = "win";
    } else {
      response = "lose";
    }
  }
  function rock() {
    buttonsVisible = false;
    userMove = "rock";
    let index = Math.floor(Math.random(0) * autoMoves.length);
    autoMove = autoMoves[index];
    if (autoMove == "rock") {
      response = "tie";
    } else if (autoMove == "scissors") {
      response = "win";
    } else {
      response = "lose";
    }
  }

  let autoMoves = ["paper", "scissors", "rock"];
</script>

<Header />

<main>
  <h2>Welcome</h2>

  <p>Paper Scissors Rock, also known as Rock Paper Scissors or simply RPS, is a popular hand game played between two individuals. The objective of the game is to select one of three possible hand gestures—rock, paper, or scissors—while simultaneously trying to predict the gesture chosen by the opponent. The game follows a set of predefined rules that determine the outcome based on the combination of gestures chosen by both players.</p>
  {#if buttonsVisible}
    <br />
    Use the box below to play!
    <br />

    <button on:click={paper}><img src="paper.png" alt="paper" /></button>
    <button on:click={scissors}><img src="scissors.png" alt="scissors" /></button>
    <button on:click={rock}><img src="rock.png" alt="rock" /></button>
  {:else}
    <br />
    You chose: {userMove}
    <br />
    The computer chose: {autoMove}
    <br />
    You {response}
  {/if}
</main>
<Footer />

<style>
  img {
    width: 40px;
  }
</style>
