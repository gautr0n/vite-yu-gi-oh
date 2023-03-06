<script>
  import axios from 'axios'

  export default {
    data(){
      return{

      }
    },
    methods: {
      yugiCards() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php') 
      }
    },
    created(){
      this.yugiCards()
    }
  }
</script>

<template>

</template>

<style scoped>
</style>
