<template>
  <div>
    <mt-field label="用户名" placeholder="请输入用户名" v-model="username"></mt-field>
    <mt-field label="密码" placeholder="请输入密码" type="password" v-model="password"></mt-field>
    <mt-button @click="doLogin">登录</mt-button>
  </div>
</template>
<script>
export default {
  methods: {
    doLogin () {
      this.$axios.put("users/" + this.username, {
        isLogin: true
      })
      .then( res => {
        this.$router.push({
          name: "music.list"
        });
      })
    }
  },
  data () {
    return {
      username: "", password: ""
    }
  }
}
</script>
<style scoped>

</style>
