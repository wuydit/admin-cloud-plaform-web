/* eslint-disable no-console */
<template>
<div id = "login" class="loginPage">
  <el-container>
    <el-header>
      <login-head/>
    </el-header>
    <el-main class="el-main">
        <login-form/>
    </el-main>

    <el-floor>
      <login-floor/>
    </el-floor>
  </el-container>
</div>
</template>

<script>
import LoginHead from './LoginHead.vue'
import LoginForm from './LoginForm.vue'
import LoginFloor from './LoginFloor.vue'
export default {
  name: 'login',
  components: {
    LoginHead,
    LoginForm,
    LoginFloor
  }
}
</script>

<style scoped>
.loginPage {
  width: 100%;
  height: auto;
  padding: 0 0; 
  box-sizing: border-box ; 
}

.el-main {
  padding: 0;
  width: 100%;
  height: auto;
  top: 60px;
  bottom: 60px;
  background-image: url('../../assets/bg.jpg');
  position: absolute; 
}

</style>
