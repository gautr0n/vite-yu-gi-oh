<script>
  import appHeader from './components/appHeader.vue'
  import appMain from './components/appMain.vue'
  import axios from 'axios'
  import store from './store'

  export default{
    components: {
      appHeader,
      appMain,
    },
    data() {
      return {
        store
      }
    },
    computed: {
      search() {
        return this.store.search
      },
    },
    watch: {
      search(newVal,oldVal) {
        console.log('i')
        this.fetchCards()
      }
    },
    methods: {
      fetchCards() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=21&offset=0&fname=' + this.store.search)
        .then(res => {
          console.log(res)
          const results = res.data.data
          this.store.cards = results
          console.log(this.store.cards)
        }).catch(() => {
          this.store.movies = []
        })
      }
    }
}
</script>


<template>
  <appHeader></appHeader>
  <appMain></appMain>
</template>


<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    text-decoration: none;
  }
</style>
