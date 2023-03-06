<script>
  import appHeader from './components/appHeader.vue'
  import appMain from './components/appMain.vue'

  export default{
    components: {
      appHeader,
      appMain,
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
