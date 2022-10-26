<template>
  <div class="home">
    <h1>Home page for rps</h1>

    <div class="hand">
      <div>
        <button @click="inhand('rock1')" id="rock1">Rock</button>
        <button @click="inhand('paper1')" id="paper1">Paper</button>
        <button @click="inhand('sciccors')" id="sciccors">Scissors</button>
      </div>

      <div id="player1">P1 = {{ output }}</div>

      <div id="player2">{{ output }} = P2</div>

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
import { onMounted } from "@vue/runtime-core";

export default {
  setup() {
    const output = ref("");
    const play = ref(false)
    
    const inhand = (rps) => {
      const p1 = document.getElementById("player1");
      const p2 = document.getElementById("player2");

      console.log(rps);
      // console.log(p1.innerHTML)
      if (p1.innerHTML) {
        output.value = rps;
      }
      if (p2.innerHTML) {
        output.value = rps;
      }
    };

    return { inhand, output , play };
    // onMounted(() => {});
  },
};
</script>
