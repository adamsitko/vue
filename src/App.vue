<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
        <div v-if=login>
          <logoff-form @login="logMeOut($event)" :email="email"></logoff-form>
        </div>
        <div v-else>
      <login-form @login="logMeIn($event)"></login-form>
      
        </div>
    
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import LogoffForm from "./LogoffForm";
export default {
  components: {LoginForm, LogoffForm},
  name: 'app',
  data () {
    return {
      email: 'email@gmail.com',
      login: false
    }
  },
  methods: {
  logMeOut(status){
    this.login = status;
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