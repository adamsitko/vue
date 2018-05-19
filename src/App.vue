<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
        <div v-if=login>
          <h2>Witaj {{email}}!</h2>
          <button @click="wyloguj()">Wychodzę</button>
        </div>
        <div v-else>
              <label>Zaloguj się e-mailem</label>
              <input type="email" v-model="email">
              <button @click="zaloguj()">Wchodzę</button>
        </div>
    
  </div>
</template>

<script>
import "milligram";

export default {
  name: 'app',
  data () {
    return {
      email: 'email@gmail.com',
      login: false
    }
  },
  methods: {
  zaloguj() {
    this.login = true;
  },
  wyloguj(){
    this.login = false;
  }
}
  
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
