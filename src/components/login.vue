<template>
  <div class="login-wrap">
    <div class="login-code">
      <img
        src="https://liang-1256974191.cos.ap-beijing.myqcloud.com/mt/login_code.png"
        class="code"
      />
      <div class="info">
        请使用微信扫描二维码登录 <br />
        “开心麻团”
      </div>
    </div>
    <div class="login-form">
      <div class="form-item">
        <span class="icon">
          <svg-icon icon-class="user" />
        </span>
        <input type="text" value="" placeholder="请输入用户名" />
      </div>
      <div class="form-item">
        <span class="icon">
          <svg-icon icon-class="password" />
        </span>
        <input type="text" value="" placeholder="请输入密码" />
      </div>
      <button class="submit">提交</button>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.login-wrap {
  display: flex;
  min-width: 600px;
  padding: 20px 0;
  .login-code {
    text-align: center;
    padding: 0 40px;
    .code {
      width: 200px;
      height: 200px;
    }
    .info {
      margin-top: 5px;
      color: #333;
      font-size: 13px;
    }
  }
  .login-form {
    padding: 0 40px;
    border-left: 1px solid #fff;
    flex: 1;
    .form-item {
      padding: 10px 15px;
      background: #fff;
      margin-bottom: 30px;
      display: flex;
      align-items: center;
      .icon {
        color: #666;
        margin-right: 15px;
      }
      input {
        flex: 1;
        outline: none;
        border: none;
        font-size: 14px;
      }
    }
    .submit {
      border: none;
      height: 42px;
      background: #333;
      color: #fff;
      display: block;
      outline: none;
      width: 100%;
      font-size: 14px;
      &:hover {
        background: #444;
      }
      &:active {
        background: #555;
      }
    }
  }
}
</style>
