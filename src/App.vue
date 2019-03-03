<template>
  <div id="app">
    <!-- 调用Element UI组件 -->
    <div class="login">
      <h3>登录</h3>账号
      <el-input placeholder="请输入内容" v-model="input10" clearable></el-input>密码
      <el-input aria-placeholder="请输入密码" v-model="input11" show-password></el-input>
      <el-row>
        <el-button type="primary">提交</el-button>
        <el-button>重置</el-button>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      input10: "",
      input11: ""
    };
  },
  // 请求数据
  mounted() {
    this.$axios.get("https://api.github.com/users").then(res => {
      console.log(res.data);
    });
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.login {
  width: 300px;
  height: 200px;
  margin: 0 auto;
}
</style>
