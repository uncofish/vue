<template>
  <div id="app">
    <img src="./assets/logo.png">
    <test></test>
   <!-- <router-view/>-->
    <div>
    <h1>测试</h1>
      <router-link to="/params/888/dx1 shuai">百度的超链接params</router-link>

      <transition name="fade">
        <keep-alive>
          <router-view></router-view>
        </keep-alive>
      </transition>

    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue"
import test from "./components/test.vue"

axios.get('http://localhost:90/helloboot/redis/getStr',{
  params:{
    ID:111
  }
}).then(function (response) {
  console.log(response)
}).catch(function (error) {
  console.log(error)
})

export default {
  name: 'App',
  components:{
    HelloWorld,
    test
  }
}




 /* const User = {
    template: '<div>Usre</div>'
  }

  const router = new VueRouter({
    routes:[
      // 动态路由参数, 以冒号开头
      {path:'/user/:id',component:User}
    ]
  })

  router.map({
    "/home":{component:HelloWorld},
    "/test":{component:test}
  })*/
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
