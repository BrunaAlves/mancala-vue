<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
import MancalaService from "./services/MancalaService";

export default {
  name: 'App',
  components: {
  },
  mounted() {
    MancalaService.getGame()
      .then(() => {
        this.$router.push("/game")
      })
      .catch(() => {
        this.$router.push("/start")
      });
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
