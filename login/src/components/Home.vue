<template>
  <div>
    <router-link :to = "{name: 'login'}">登录</router-link>
    <router-link :to = "{name: 'music'}">我的音乐</router-link>
    <router-link :to = "{name: 'list'}">音乐列表</router-link>    
    <mt-button type = "danger" size = "small" @click = "exit">退出</mt-button>
    <router-view></router-view>  
  </div>
</template>
<script>
export default {
  methods: {
    exit () {
      this.$axios.put("users/god", {
        isLogin: false
      })
      .then( res => {
        this.$router.push({
          name: "login"
        });
      });
    }
  },
  data () {
    return {
      
    }
  }
}
</script>
