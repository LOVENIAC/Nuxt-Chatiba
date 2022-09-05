<template>
  <div>
    I am search!<br/>
    {{ ques }}<br />
    <nuxt-link
      v-for="(item,index) in quesList"
      :key="index"
      :to = "{
        name: 'q-id',
        params: {
          id: item.id
        }
      }"
      target="_blank"
    >
      <div>
        {{ item.ques }}
        <div v-for="(option,key) in item.options" :key="key">
          {{ key }}. {{ option }}
        </div>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
  import $axios from 'axios'
  export default {
    // middleware: 'auth',
    data(){
      return{
        ques: '',
        quesList: []
      }
    },
    // async asyncData({ query : { ques = '' },$axios}){
    //   let res = await $axios({url:'/data/quesList.json'});
    //   console.log(ques,res.data);
    //   return {
    //     ques,
    //     quesList: res.data
    //   }
    // },
    mounted(){
      $axios({url:'/data/quesList.json'}).then((res)=>{
        this.quesList = res.data;
      });
    }
  }
</script>

<style>

</style>