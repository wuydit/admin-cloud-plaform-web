/* eslint-disable no-console */
<template>
  <div class="login-form">
    <el-form :model="formLogin" :rules="rules" ref="formLogin" label-width="100px" class="formLogin ">
      <el-form-item label="用户名" prop="username">
        <el-input type="string" v-model="formLogin.username"></el-input>
      </el-form-item>
      <el-form-item label="密码" prop="pwd">
        <el-input type="password" v-model="formLogin.pwd"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button size="medium" type="primary" @click="submitForm('formLogin')">登录</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
      var checkUsername = (rule, value, callback) => {
        if (value === '') {
          return callback(new Error('用户名不能为空'));
        }
      };
      var validatePassword = (rule, value, callback) => {
        if (value === '') {
          return callback(new Error('请输入密码'));
        }
      };
      return {
        formLogin: {
          username: '',
          pwd: ''
        },
        rules: {
          username: [
            { validator: checkUsername, trigger: 'blur' }
          ],
          pwd: [
            { validator: validatePassword, trigger: 'blur' }
          ]
        }
      };
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!');
          } else {
            // eslint-disable-next-line no-console
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
}
</script>

<style scoped>
body {
  color: #373d41;
  line-height: 1.28571;
}
.login-form {
    float: right;
    margin-top: 60px;
    margin-right: 60px;
    padding: 20px;
    background-color: aliceblue;
    width: 40%;
    height: 50%;
}
</style>
