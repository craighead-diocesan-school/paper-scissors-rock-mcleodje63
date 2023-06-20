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

<main>
  <Header />
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
    You chose: <img src="{userMove}.png" alt={userMove} />
    <br />
    The computer chose: <img src="{autoMove}.png" alt={autoMove} />
    <br />
    You {response}
  {/if}

  {#if response == "lose"}<img src="tobey.webp" alt="Tobey Maguire" />
  {:else if response == "win"}<img src="theWeeknd.gif" alt="The Weeknd" />
  {:else if response == "tie"}<img src="tie.gif" alt="tie" />{/if}

  <Footer />
</main>

<style>
  main {
    margin-left: auto;
    margin-right: auto;
    display: block;
    width: 100vh;
    text-align: center;
  }
  img {
    width: 100px;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
</style>
