<template>
  <div class="home">
    <h1>Home page for rps</h1>

    <div class="hand">
      <div>
        <button @click="inhand('rock1')" id="rock1">Rock</button>
        <button @click="inhand('paper1')" id="paper1">Paper</button>
        <button @click="inhand('scissors1')" id="scissors">Scissors</button>
      </div>

      <div id="player1">P1 = {{ output1 }}</div>

      <div id="player2">{{ output2 }} = P2</div>

      <div>
        <button @click="inhand('rock2')" id="rock2">Rock</button>
        <button @click="inhand('paper2')" id="paper2">Paper</button>
        <button @click="inhand('scissors2')" id="scissors3">Scissors</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.home {
  max-width: 700px;
  margin: 0 auto;
}
.hand {
  display: flex;
  /* flex-flow: column; */
  justify-content: space-around;
  align-items: center;
}
.hand button {
  margin: 20px auto;
  padding: 20px;
  display: block;
  width: 100px;
  /* height: 100px; */
  box-sizing: border-box;
  /* align-self: center; */
}
</style>

<script>
import { ref } from "@vue/reactivity";

export default {
  setup() {
    const output1 = ref("");
    const output2 = ref("");
    const play = ref(false);
    const p1 = document.getElementById("player1");
    const p2 = document.getElementById("player2");

    // Who wins

    const whoWins = () => {
      setTimeout(() => {
        output1.value = "";
        output2.value = "";
      }, 1000);
    };

    // the alert
    const alertFunction = (answer) => {
      setTimeout(() => {
        alert(`${answer}`)
      },500)
    };

    // In the hand of the player

    const inhand = (rps) => {
      console.log(rps);
      if (rps.includes("1")) {
        output1.value = rps.replace("1", "");
      }
      if (rps.includes("2")) {
        output2.value = rps.replace("2", "");
      }

      // Checks who won

      (function checking() {
        if (output1.value == output2.value) {
          alertFunction("It is Draw")
          whoWins();
        } else if (output1.value == "rock" && output2.value == "paper") {
          alertFunction("Player 2 WIns");
          whoWins();
        } else if (output1.value == "rock" && output2.value == "scissors") {
          alertFunction("Player 1 WIns");
          whoWins();
        } else if (output1.value == "paper" && output2.value == "scissors") {
          alertFunction("Player 2 WIns");
          whoWins();
        } else if (output1.value == "paper" && output2.value == "rock") {
          alertFunction("Player 1 WIns");
          whoWins();
        } else if (output1.value == "scissors" && output2.value == "paper") {
          alertFunction("Player 1 WIns");
          whoWins();
        } else if (output1.value == "scissors" && output2.value == "rock") {
          alertFunction("Player 2 WIns");
          whoWins();
        } 
      })();
    };

    return { inhand, output1, output2, play };
  },
};
</script>
