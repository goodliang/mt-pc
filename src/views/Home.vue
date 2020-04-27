<template>
  <div class="home-container">
    <div class="header">
      <div class="logo">
        <img
          src="https://liang-1256974191.cos.ap-beijing.myqcloud.com/mt/mt_logo.png"
          alt=""
          class="src"
        />
        <h2>开心麻团</h2>
      </div>
      <div class="title">草根的开团神奇</div>
    </div>
    <div class="body">
      <h1>你的农特超级管家</h1>
      <p class="des">在这里，把家乡的真正地道，传达给每一个热爱生活的人。</p>
      <div class="btn-group">
        <button @click="isLogin = true">商家登录</button>
        <button @click="isLogin = true">供应商登录</button>
        <button class="dark-btn" @click="isAbout = true">关于我们</button>
      </div>
    </div>
    <div class="footer">
      Copyright © 北京开心麻团科技有限公司. All Rights Reserved.|
      蜀ICP备11008632号
    </div>
    <modal :visible.sync="isLogin">
      <login></login>
    </modal>
    <modal :visible.sync="isAbout" title="关于我们">
      <div class="About">
        The Walt Disney Company，together with its subsidiaries and
        affiliates，is a leading diversified international entertainment and
        media enterprise with four business segments. Disney's first animation
        screened in China in the 1930s and today our long association continues
        with offices in Beijing， Shanghai and Guangzhou with over 3000
        employees.
      </div>
    </modal>
  </div>
</template>

<script>
import modal from "../components/modal";
import login from "../components/login";
export default {
  name: "Home",
  data() {
    return {
      isLogin: false,
      isAbout: false
    };
  },
  components: {
    modal,
    login
  }
};
</script>
<style lang="scss" scoped>
@import "../style/mixin";
.home-container {
  width: 100vw;
  height: 100vh;
  background: url("https://liang-1256974191.cos.ap-beijing.myqcloud.com/mt/shuiguo_bg.png")
    center bottom;
  background-size: cover;
  position: relative;
  .header {
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    @include flex();
    padding: 30px;
    .logo {
      @include flex(flex-start);
      img {
        width: 44px;
        height: 44px;
        margin-right: 20px;
      }
      h2 {
        font-size: 22px;
        flex: 1;
      }
    }
    .title {
      font-size: 22px;
      color: #333;
      font-weight: 300;
    }
  }
  .body {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(50px, -50%);
    padding: 0 50px;
    h1 {
      font-size: 46px;
      font-weight: bold;
    }
    .des {
      padding-top: 20px;
      color: #444;
    }
    .btn-group {
      padding-top: 50px;
      button {
        border: none;
        height: 42px;
        background: #fff;
        color: #333;
        display: inline-block;
        margin-right: 15px;
        outline: none;
        min-width: 120px;
        padding: 0 20px;
        text-align: center;
        font-size: 14px;
        cursor: pointer;
        &:hover {
          background: #f1f1f1;
        }
        &:active {
          background: #e9e9e9;
        }
      }
      .dark-btn {
        background: rgba(255, 255, 255, 0.5);
      }
    }
  }
  .footer {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 30px;
    text-align: right;
    font-size: 14px;
    color: #666;
  }
  .About {
    width: 500px;
    color: #333;
    line-height: 1.6;
  }
}
</style>
