<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <button @click="getDemoList">点击调接口</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  methods: {
    getDemoList () {
      this.axios({
        method: 'get',
        url: '/parameter/query'
      })
        .then(res => {
          console.log(res)
        })
        .catch(resp => {
          console.log('请求失败：' + resp.status + ',' + resp.statusText)
        })
    }
  }
}
</script>
