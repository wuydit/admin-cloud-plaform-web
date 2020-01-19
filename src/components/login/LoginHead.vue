/* eslint-disable no-console */
<template>
    <div class="login-toobar">
        <div class="login-toobar-header">
            <div class="login-toobar-element">
                <span class="topbar-text">登录</span>
            </div>
        </div>
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.login-toobar-header {
    margin: 0 auto;
    max-width: 1200px;
    height: 100%;
    box-sizing: border-box;
    padding: 26.5px 0;
    position: relative;
    z-index: 2000;
}
.login-toobar {
    box-shadow: 0 0px 0px 0 rgba(0,0,0,.1);
    box-sizing: border-box;
    height: 80;
    width: 100%;
    position: relative;
    z-index: 1000;
    clear: both;
}
.login-toobar .login-toobar-header .login-toobar-element{
    float: left;
}
.login-toobar .login-toobar-header .login-toobar-element .topbar-text {
    text-align: left;
    font-size: 24px;
    color: #181818;
    letter-spacing: 0;
    display: inline-block;
    padding: 0 10px;
    vertical-align: bottom;
    border-left: 1px solid #999;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}
</style>
