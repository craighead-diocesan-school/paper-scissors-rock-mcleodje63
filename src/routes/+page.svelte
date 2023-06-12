<script>
  import Header from "$lib/Header.svelte";
  import Footer from "$lib/Footer.svelte";
  let userMove;
  function game() {
    userMove = userMove.toLowerCase();
    //   if (userMove == "paper") {
    //   }
    //   if (userMove == "rock") {
    //   }
    //   if (userMove == "scissors") {
    //   }

    //
  }
</script>

<Header />

<main>
  <h2>Welcome</h2>

  <p>Paper Scissors Rock, also known as Rock Paper Scissors or simply RPS, is a popular hand game played between two individuals. The objective of the game is to select one of three possible hand gestures—rock, paper, or scissors—while simultaneously trying to predict the gesture chosen by the opponent. The game follows a set of predefined rules that determine the outcome based on the combination of gestures chosen by both players.</p>
  <br />
  Use the box below to play!
  <br />
  <input bind:value={userMove} /><button on:click={game}>Click here</button>
</main>

<Footer />
