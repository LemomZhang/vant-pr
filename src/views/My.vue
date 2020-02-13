<template>
  <div>
    <div class="login-holder">
      <!--新加手机登录-->
      <h3 class="title">欢迎来到小游游戏</h3>
      <van-field v-model="tel"
                 type="tel"
                 label="手机号"
                 placeholder="请输入手机号" />
      <van-field v-model="sms"
                 center
                 clearable
                 label="短信验证码"
                 placeholder="请输入短信验证码">
        <van-button slot="button"
                    size="small"
                    plain
                    round
                    color="#ff4e1e"
                    type="primary">获取验证码</van-button>
      </van-field>
      <div class="login">
        <van-button round
                    color="linear-gradient(to right, #ff4800, #ff7800)"
                    block>立刻登录/注册</van-button>
      </div>
      <div class="change-login">
        <div>其他方式登陆</div>
        <a class="qq_login"
           href="https://graph.qq.com/oauth2.0/authorize?response_type=code&amp;client_id=101178313&amp;redirect_uri=http://www.fhyx.com/callback/index/s/mobile?url=m.fhyx.com">
          <img src="http://m.fhyx.com/img/application/QQlogin.png"
               alt="">
          <span>QQ</span>
        </a>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      tel: '',
      sms: ''
    };
  }
};
</script>

<style lang="scss" scoped>
.login-holder {
  display: flex;
  margin-top: 10rem;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1rem;
  > .title {
    margin-bottom: 1rem;
  }
  > .login {
    margin-top: 1rem;
    width: 100%;
  }
  > .change-login {
    margin-top: 2rem;
    > .qq_login {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-left: 2rem;
      width: 2rem;
      img {
        margin-top: 0.4rem;
        width: 1rem;
      }
      span {
        font-size: 0.5rem;
      }
    }
  }
}
</style>