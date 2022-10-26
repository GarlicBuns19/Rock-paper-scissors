<template>
  <div class="home">
    <h1>Home page for rps</h1>

    <div class="hand">
      <div>
        <button>Rock</button>
        <button>Paper</button>
        <button>Scissors</button>
      </div>

      <div>
        P1
      </div>

      <div>
        P2
      </div>

      <div>
        <button>Rock</button>
        <button>Paper</button>
        <button>Scissors</button>
      </div>
    </div>
    
  </div>
</template>

<style scoped>
.home{
  max-width: 700px;
  margin: 0 auto;
}
.hand{
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
export default {};
</script>
