<script>
  import Header from "$lib/Header.svelte";
  import Footer from "$lib/Footer.svelte";
  let userMove = "";
  function paper() {
    userMove = "paper";
    let autoMoves = ["paper", "scissors", "rock"];
    let autoMove;
    let index = Math.floor(Math.random(0) * autoMoves.length);
    autoMove = autoMoves[index];
  }
  function scissors() {
    userMove = "scissors";
    let autoMoves = ["paper", "scissors", "rock"];
    let autoMove;
    let index = Math.floor(Math.random(0) * autoMoves.length);
    autoMove = autoMoves[index];
  }
  function rock() {
    userMove = "rock";
    let autoMoves = ["paper", "scissors", "rock"];
    let autoMove;
    let index = Math.floor(Math.random(0) * autoMoves.length);
    autoMove = autoMoves[index];
  }
  let autoMoves = ["paper", "scissors", "rock"];
  let autoMove;
  let index = Math.floor(Math.random(0) * autoMoves.length);
  autoMove = autoMoves[index];
</script>

<Header />

<main>
  <h2>Welcome</h2>

  <p>Paper Scissors Rock, also known as Rock Paper Scissors or simply RPS, is a popular hand game played between two individuals. The objective of the game is to select one of three possible hand gestures—rock, paper, or scissors—while simultaneously trying to predict the gesture chosen by the opponent. The game follows a set of predefined rules that determine the outcome based on the combination of gestures chosen by both players.</p>
  <br />
  Use the box below to play!
  <br />
  <button on:click={paper}><img src="paper.png" alt="paper" /></button>
  <button on:click={scissors}><img src="scissors.png" alt="paper" /></button>
  <button on:click={rock}><img src="rock.png" alt="paper" /></button>
  <br />
  You chose: {userMove}
  <br />
  The computer chose: {autoMove}
</main>
<Footer />

<style>
  img {
    width: 40px;
  }
</style>
