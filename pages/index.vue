<template>
  <div class="content">
    <div class="logo">
      <img src="~assets/image/logo.png" alt="查题吧">
    </div>
    <div class="search">
      <input autocomplete="off" v-model="queryText" @keyup.enter="queryQues()" class="search-input" placeholder="在 16,952,858 道题目中搜索..." type="text">
      <div class="search-btn" @click="queryQues()">
        <svg viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg">
          <path fill="#aeaeae" d="M953.474215 908.234504l-152.576516-163.241391c61.92508-74.48211 95.81186-167.36973 95.81186-265.073744 0-229.294809-186.63531-415.930119-416.102133-415.930119-229.294809 0-415.930119 186.63531-415.930119 415.930119s186.63531 415.930119 415.930119 415.930119c60.032925 0 118.00168-12.55703 172.186125-37.327062 16.169326-7.396607 23.221905-26.318159 15.825298-42.315471-7.396607-16.169326-26.318159-23.221905-42.315471-15.825298-45.927768 20.813707-94.951789 31.478582-145.695952 31.478582-194.031917 0-351.94087-157.908953-351.94087-351.94087 0-194.031917 157.908953-351.94087 351.94087-351.94087 194.031917 0 351.94087 157.908953 351.94087 351.94087 0 91.339493-34.918864 177.86259-98.048043 243.743995-12.213002 12.729044-11.868974 33.026709 0.860071 45.239711 1.032085 0.860071 2.236183 1.204099 3.268268 2.064169 0.860071 1.204099 1.376113 2.752226 2.408198 3.956325l165.477574 177.00252c6.192508 6.70855 14.793214 10.148833 23.393919 10.148833 7.912649 0 15.653284-2.92424 21.845792-8.600706C964.827146 941.433227 965.515202 921.135562 953.474215 908.234504z" />
        </svg>
      </div>
    </div>
    <button @click="hideToApp()">toggle toApp</button>
  </div>
</template>

<script>
  export default {
    data(){
      return{
        queryText:''
      }
    },
    methods:{
      queryQues(){
        if(!this.queryText.trim()){
          alert('请输入正确的题目..');
          return;
        }
        this.$router.push({
          path:'/search',
          query:{
            ques:this.queryText
          }
        }); 
      },
      hideToApp(){
        // this.$store.state.toAppStatus = !this.$store.state.toAppStatus;
      }
    }
  }
</script>

<style lang="less" scoped>
  .content {
    width:fit-content;
    padding-top: 100px;
    margin: 0 auto;
  }
  /* logo */
  .logo {
    width: fit-content;
    margin: 0 auto;
    img{
      width: 300px;
    }
  }
  /* 搜索框 */
  .search {
    width: 700px;
    margin: 70px auto 50px;
    display: flex;
    margin-top: 20px;
    padding: 10px;
    height: 60px;
    border-radius: 15px;
    border: 2px solid #aeaeae;
    &:hover {
      border-color: #3c7cfc;
      box-shadow: 0px 5px 12px 0px rgba(0, 0, 0, 0.16);
    }
    input {
      line-height: 18px;
      font-size: 18px;
      font-weight: 400;
      height: 100%;
      width: 95%;
      border: none;
      outline: none;
      &::placeholder {
        color: #aeaeae;
      }
    }
    .search-btn {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 5%;
      svg{
        width: 90%;
      }
    }
  }
</style>
