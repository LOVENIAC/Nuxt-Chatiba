<template>
  <div>
    <myHeader />
    <nuxt class="container-wrapper" />
    <myFooter />
  </div>
</template>

<script>
  import myHeader from '../components/Header'
  import myFooter from '../components/Footer'

  export default {
    components:{
      myHeader,
      myFooter
    }
  }
</script>

<style>
  .container-wrapper{
    min-height: calc(100vh - 120px);
  }
</style>
