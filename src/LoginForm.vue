<template>
   <div>
       <label>Zaloguj się e-mailem</label>
       <input type="email" v-model="email">
       <button @click="enter()">{{buttonLabelDisp}}</button>
   </div>
</template>

<script>
export default {
props: ['buttonLabel'],

/*
    mounted() {
        if (!this.buttonLabel) {
            this.buttonLabel = 'Zaloguj się';
        }
    }, 
*/
    data() {
        return {
            email: ''
        }
    },

    methods: {
        enter() {
             this.$emit('login', this.email);
        },     
    },

    computed: {
        buttonLabelDisp() {
            return this.buttonLabel || 'Zaloguj się';  
        }
    },
}
</script>