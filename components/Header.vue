<template>
  <div class="header">
    <div class="nav-bar">
      <div class="logo">
        <img @click="goHome()" src="~assets/image/logo.png" alt="查题吧">
      </div>
      <div class="nav">
        <nuxt-link
          v-for="(menu,index) in menuList"
          :key="index"
          :to="menu.link"
          >{{menu.name}}
        </nuxt-link>
      </div>
      <div class="loginbar">
          <div v-if="!isLogin" class="loginbar-warpper">
              <div class="loginbar-btn">登录</div>
              <div class="loginbar-btn regist">注册</div>
          </div>
          <div v-else class="loginbar-warpper">
            <div class="loginbar-btn">退出</div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name:'myHeader',
    data(){
      return{
        isLogin: false,
        menuList:[
          {name:'题库分类',link:'/subject'},
          {name:'网课答案',link:'/course'},
        ]
      }
    },
    methods:{
      goHome(){
        this.$router.push('/');
      }
    }
  }
</script>

<style lang="less">
  /* Header */
  .header {
    min-width: 1220px;
    height: 60px;
    width: 100%;
    box-shadow: 0px 5px 12px 0px rgba(0, 0, 0, 0.16);
  }
  .nav-bar {
    max-width: 1200px;
    min-width: 700px;
    position: relative;
    line-height: 60px;
    margin: 0 auto;
    display: flex;
    .logo {
      margin-right: 20px;
      img {
        height: 40px;
        cursor: pointer;
      }
    }
  }
  .nav {
    font-size: 18px;
    font-weight: 450;
    display: inline-flex;
    a{
      display: block;
      margin-right: 20px;
      &.active,&:hover{
        color: #3c7cfc;
      }
    }
  }
  /* Header 登录 */
  .loginbar {
    font-size: 16px;
    height: 100%;
    position: absolute;
    right: 0;
  }
  .loginbar-warpper {
    height: 100%;
    user-select: none;
    display: flex;
    align-items: center;
  }
  .loginbar-btn {
    cursor: pointer;
    text-align: center;
    border-radius: 20px;
    line-height: 36px;
    width: 70px;
    height: 36px;
    margin-right: 20px;
    border: 1px solid #3c7cfc;
    color: #3c7cfc;
    &:hover {
      box-shadow: 0px 5px 12px 0px rgba(0, 0, 0, 0.16);
    }
  }
  .regist {
    background-color: #3c7cfc;
    color: white;
  }
</style>