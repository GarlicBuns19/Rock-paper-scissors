<template>
  <div class="home">
    <h1>Home page for rps</h1>

    <div class="hand">
      <div>
        <button @click="inhand('rock1')" id="rock1">Rock</button>
        <button @click="inhand('paper1')" id="paper1">Paper</button>
        <button @click="inhand('sciccors1')" id="sciccors">Scissors</button>
      </div>

      <div id="player1">P1 = {{ output1 }}</div>

      <div id="player2">{{ output2 }} = P2</div>

      <div>
        <button @click="inhand('rock2') " id="rock2">Rock</button>
        <button @click="inhand('paper2')" id="paper2">Paper</button>
        <button @click="inhand('scissors3')" id="scissors3">Scissors</button>
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
    const play = ref(false)
    const p1 = document.getElementById("player1");
    const p2 = document.getElementById("player2");
    
    const inhand = (rps) => {
      console.log(rps);
      if (rps.includes('1')) {
        output1.value = rps;
      }
      if (rps.includes('2')) {
        output2.value = rps;
      }
    };

    return { inhand, output1 , output2 , play };
  },
};
</script>
