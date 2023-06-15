<script>
  import Header from "$lib/Header.svelte";
  import Footer from "$lib/Footer.svelte";
  let userMove = "";
  let response = "";
  // function paper() {
  //   userMove = "paper";
  // }
  // function scissors() {
  //   userMove = "scissors";
  // }
  // function rock() {
  //   userMove = "rock";
  // }
  function game() {
    if (userMove === "paper.png") {
      let response = "paper";
    } else if (userMove === "scissors.png") {
      let response = "scissors";
    } else if (userMove === "rock.png") {
      let response = "rock";
    }
  }
  let autoMoves = ["paper", "scissors", "rock"];
  let autoMove;
  let index = Math.floor(Math.random() * autoMoves.length);
  autoMove = autoMoves[index];
</script>

<Header />

<main>
  <h2>Welcome</h2>

  <p>Paper Scissors Rock, also known as Rock Paper Scissors or simply RPS, is a popular hand game played between two individuals. The objective of the game is to select one of three possible hand gestures—rock, paper, or scissors—while simultaneously trying to predict the gesture chosen by the opponent. The game follows a set of predefined rules that determine the outcome based on the combination of gestures chosen by both players.</p>
  <br />
  Use the box below to play!
  <br />
  <button on:click={game}><img src="paper.png" alt="paper" /><input type="text" bind:value={userMove} /></button>
  <button on:click={game}><img src="scissors.png" alt="scissors" /><input type="text" bind:value={userMove} /></button>
  <button on:click={game}><img src="rock.png" alt="rock" /><input type="text" bind:value={userMove} /></button>
  <br />
  You chose: {response}
  <br />
  The computer chose: {autoMove}
</main>
<Footer />

<!-- <script>
  import Header from "$lib/Header.svelte";
  import Footer from "$lib/Footer.svelte";
  let userMove = "";
  function paper() {
    userMove = "paper";
  }
  function scissors() {
    userMove = "scissors";
  }
  function rock() {
    userMove = "rock";
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
</style> -->

<style>
  img {
    width: 40px;
  }
</style>
