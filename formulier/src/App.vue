<script>
import oefening from './components/oefening.vue'
export default{
  data(){
    return{
      inputText: ''
    }
  },

  methods: {
    submitForm(){
      alert('Inzenden van formulier opgevangen');
      console.log('Inzenden van formulier opgevangen');
    },
    enterToets(){

    }
  },

  components: {
    oefening
  }
}
</script>

<template>
  <div class="container">
    <form @submit.prevent="submitForm">
      <label for="subscribe">Schrijf je in op de nieuwsbrief</label>
      <input v-model="inputText" type="text" @keyup.enter="enterToets" name="firstName" id="subscribe">
      <button >Schrijf je in</button>
      <p v-if="inputText">{{inputText}}</p>
    </form>
  </div>

  <oefening></oefening>
</template>

<style scoped>

</style>
