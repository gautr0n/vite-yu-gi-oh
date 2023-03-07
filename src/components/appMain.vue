<script>
  import axios from 'axios'

  import cardsList from './cardsList.vue'

  export default {
    components:{
      cardsList,
    },
    data(){
      return{
        cards: []
      }
    },
    methods: {
      yugiCards() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php').then((res) => {
          console.log(res.data.data)
          this.cards = res.data.data
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
      <div class="cards-founded">Founded {{ cards.length }} cards</div>
      <ul>
        <cardsList v-for="element in cards" :key="element.id" :archetype="element.archetype" :name="element.name" :image="element.cards_images.image_url"></cardsList>
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
      justify-content: space-between;    
    }
  }
}

</style>
