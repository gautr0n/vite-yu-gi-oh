<script>
  import store from '../store'
  export default {
    data() {
      return  {
        store,
        changeCard: ''
      }
    },
    methods: {
      searchCard() {
        this.store.search = this.changeCard
      }
    }
  }
</script>

<template>
    <div>
        <div>
            <img src="https://th.bing.com/th/id/R.1eefcc8ef1475ad8cd8b3e169675cff2?rik=w3p0b4nea0cZGw&pid=ImgRaw&r=0" alt="">
            <h1>Yu-gi-oh Api</h1>        
        </div>
        <div>
            <input type="text" placeholder="cerca una carta" @keyup.enter="searchCard" v-model="changeCard">
            <button @click="searchCard">Invio</button>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    div {
        display: flex;
        align-items: center;
        padding: 5px;
        img {
            height: 50px;
        }
    }
</style>
