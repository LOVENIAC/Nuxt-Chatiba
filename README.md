## 安装
```
npx create-nuxt-app xxx(项目名)
```
## 开发环境
```
npm run dev
```

# 生命周期
  ## 服务端钩子 SSR
  ### nuxtServerInit
    参数:sotre,context  
    适用场景:store的初始化操作
  ### middleware
    适用场景:路由守卫  
    中间件执行顺序:nuxt.config.js>匹配布局(layout)>匹配页面(pages)
  ### validate
    适用场景:参数校验  
    需返回boolean,ture正常返回页面,false默认跳转404
  ### asyncData
    适用场景:向服务端请求获取数据，返回给组件（异步）  
    通过**return{key:value}方式**返回给组件
  ### fetch
    适用场景:向服务端请求获取数据，提交给vuex(store)（异步）

  ## 服务端和客户端钩子 SSR&CSR
    ### beforecreate
    ### created

  ## 客户端钩子 CSR
    ### Vue基本钩子 (before)mounted、(before)update、(before)destroyed等

# 路由
  ## 约定式
    展示区:<nuxt />

    声明式跳转:<nuxt-link :to="{name:'q-id',params:{id:3},query:{text:'Hello World!'}}">
      name:路由名
      params:key对应文件名
    
    子路由:
      目录代表子路由，子路由由同级的文件，代表是同级的一级路由

    展示区层级控制
    | PATH              | FILE              |
    | :-------------    | :-------------    |
    | '/'               | 'index.vue'       |
    | '/fruit'          | 'fruit/index.vue' |
    | '/fruit/123'      | 'fruit/_id.vue'   |
    | '/fruit/detail'   | 'fruit/detail.vue'|

    pages/一级展示区/二级展示区
                  /index.vue 会在一级展示
                  /index.vue 代表有默认页面不会寻找其他_详情.vue

# 数据交互 跨域问题
  ## axios
    安装：npm i @nuxtjs/axios @nuxtjs/proxy --save