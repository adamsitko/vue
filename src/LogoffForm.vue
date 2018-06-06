<template>
   <div>
       <h2>Witaj {{printEmail}}!</h2>
       <button @click="enter()">{{buttonLabelDisp}}</button>
   </div>
</template>

<script>
export default {
props: ['email', "buttonLabel"],

    data() {
        return {
        }
    },

    methods: {
        enter() {
             this.$emit('login', false);
        },     
    },

    computed: {
        buttonLabelDisp() {
            return this.buttonLabel || 'Wyloguj się';  
        },
        printEmail(){
        return this.email || 'nieznajomy';
        },
    },


}
</script>