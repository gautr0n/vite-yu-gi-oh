<script>
  export default{
    props:{
      archetype: {
        type: String,
      },
      name: {
        type: String,
      },
      image: {
        type: String,
      }
    }
  }
</script>

<template>
    <li>
        <img src="https://images.ygoprodeck.com/images/cards/34541863.jpg" alt="">
        <div class="info-box">
          <div>{{name}}</div>
          <div>{{archetype}}</div> 
        </div>
      </li>
</template>

<style lang="scss" scoped>
    li{
        list-style: none;
        text-align: center;
        border: 2px solid black;
        width: 200px;
        margin-bottom: 30px;
        background-color: #D48F38;
        img{
        width: 100%;
        }
        div{
        padding: 15px;
        }
    }  
</style>