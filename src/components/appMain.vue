<script>
  import axios from 'axios'
  import store from '../store'
  import cardsList from './cardsList.vue'

  export default {
    components:{
      cardsList,
      store,
    },
    data(){
      return{
        store,
      }
    },
    methods: {
      yugiCards() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=21&offset=0').then((res) => {
          store.cards = res.data.data
          console.log(store);
        }) 
      }
    },
    created(){
      this.yugiCards()
    }
  }
</script>

<template>
  <main>
    <div class="container">
      <div class="cards-founded">Founded {{ store.cards.length }} cards</div>
      <ul>
        <cardsList v-for="element in store.cards" :key="element.id" :archetype="element.archetype" :name="element.name" :image="element.card_images[0].image_url"></cardsList>
      </ul>      
    </div>
  </main>

</template>

<style lang="scss" scoped>
main{
  background-color: #D48F38;
  padding: 50px;
  .container{
    background-color: white;
    padding: 30px;
    .cards-founded{
      background-color: #212529;
      color: white;
      font-weight: bold;
      padding: 15px;
    }
    ul{
      display: flex;
      flex-wrap: wrap;
      justify-content:space-between
    }
  }
}

</style>
