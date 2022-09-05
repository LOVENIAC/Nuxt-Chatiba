<template>
  <div>
    {{ id }}
  </div>
</template>

<script>
  export default {
    data(){
      return{
        id: 0
      }
    },
    asyncData({params}){
      const { id } = params;
      return {
        id
      }
    }
  }
</script>

<style>

</style>