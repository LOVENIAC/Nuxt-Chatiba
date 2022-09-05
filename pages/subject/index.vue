<template>
  <div>
    <h1>I am subject page!</h1>
    <nuxt-link
      v-for="item in subjectList"
      :key="item.id"
      :to="{
        name: 'subject-id',
        params: {
          id: item.id
        }
      }"
    >
      {{ item.subject }}
    </nuxt-link>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        subjectList: []
      }
    },
    async asyncData({$axios}) {
      let res = await $axios({
        url: '/data/subject.json'
      });
      return {
        subjectList: res.data
      }
    },
  }
</script>

<style>

</style>