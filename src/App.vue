<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
        <div v-if=login>
          <h2>Witaj {{email}}!</h2>
          <button @click="wyloguj()">Wychodzę</button>
        </div>
        <div v-else>
      <login-form @login="logMeIn($event)"></login-form>
      <login-form @login="logMeIn($event)" :button-label="'Zaloguj się jak człowiek'"></login-form>
        </div>
    
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
  components: {LoginForm},
  name: 'app',
  data () {
    return {
      email: 'email@gmail.com',
      login: false
    }
  },
  methods: {
  wyloguj(){
    this.login = false;
  },
  logMeIn(username) {
  this.email = username;
  this.login = true;
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