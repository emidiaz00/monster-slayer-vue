<template>
  <body>
    <header>
      <h1>Monster Slayer</h1>
    </header>
    <div id="game">
      <section id="monster" class="container">
        <h2>Monster Health</h2>
        <div class="healthbar">
          <div class="healthbar__value" :style="monsterBarStyes"></div>
        </div>
      </section>
      <section id="player" class="container">
        <h2>Your Health</h2>
        <div class="healthbar">
          <div class="healthbar__value" :style="playerBarStyes"></div>
        </div>
      </section>
      <section id="controls">
        <button @click="attackMonster">ATTACK</button>
        <button @click="attackMonster">SPECIAL ATTACK</button>
        <button >HEAL</button>
        <button >SURRENDER</button>
      </section>
      <section id="log" class="container">
        <h2>Battle Log</h2>
        <ul></ul>
      </section>
    </div>
  </body>
</template>

<script>
export default {
  data() {
    return {
      monsterHealth: 100,
      playerHealth: 100,
    }
  },
  computed: {
    monsterBarStyes() {
      return {width: this.monsterHealth + '%' }
      
    },
    playerBarStyes() {
      return {width: this.playerHealth + '%' }
    },
  },
  methods: {
    attackMonster() {
      const attackValue = Math.floor(Math.random() * (10 - 5)) + 5
      this.monsterHealth -= attackValue
      this.attackPlayer()
    },
    attackPlayer() {
      const attackValue = Math.floor(Math.random() * (35 - 15)) + 5
      this.playerHealth -= attackValue
    }
  },
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
