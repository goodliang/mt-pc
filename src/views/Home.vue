<template>
  <div class="home-container">
    <div class="header">
      <div class="logo">
        <img src="https://liang-1256974191.cos.ap-beijing.myqcloud.com/mt/logo.png" alt class="src" />
        <h2>开心麻团</h2>
      </div>
      <div class="title">草根的开团神奇</div>
    </div>
    <div class="body">
      <h1>最懂你的订单管理与营销助手</h1>
      <div class="des">
        <p>订单太多总是丢，客户人太少产品传播不方便，来回问又耗时间</p>
        <p>马上拥有自己的专属小程序，维护扩展你的私域流量</p>
      </div>
      <div class="btn-group">
        <button @click="isLogin = true">商家登录</button>
        <button @click="isLogin = true">供应商登录</button>
        <button class="dark-btn" @click="isAbout = true">关于我们</button>
      </div>
    </div>
    <div class="footer">
      北京原子动力网络技术有限公司 地址：北京市海淀区交大东路瑞宏写字楼301室
      服务专线：13260022690 负责人：孙磊 业务邮箱：264406@qq.com
      京ICP备13020824号
    </div>
    <modal :visible.sync="isLogin">
      <login></login>
    </modal>
    <modal :visible.sync="isAbout" title="关于我们">
      <div class="About">
        <p>
          北京原子动力网络技术有限公司以高科技为起点、以技术为核心、以强大的技术队伍为支撑，致力于为政府、企业上网提供高质量多层次的电子商务服务。我们秉着客户第
          一、服务第一的原则，全心全意为您提供最好的企业解决方案。因为我们知道，只有您对我们的大力支持，我们才会有发展的基础。
        </p>
        <p>我们的团队从成立之日起就有明确的品牌意识，打造原子品牌，</p>
        <!-- 不管了 -->
        <p>在提供优质产品的同时，我们更注重咨询服务和售后技术支持服务，我们坚持技术和咨询两条腿走。尽善尽美的服务和优先保证顾客投资回报的经营理念是我们取信于客户的法宝。团结协作、求是创新、务实拼搏、精益求精的精神是我们成就事业的基石。</p>
      </div>
    </modal>
  </div>
</template>

<script>
import modal from '../components/modal'
import login from '../components/login'
export default {
  name: 'Home',
  data() {
    return {
      isLogin: false,
      isAbout: false
    }
  },
  components: {
    modal,
    login
  }
}
</script>
<style lang="scss" scoped>
// mixin
@import '../style/mixin';
.home-container {
  width: 100vw;
  height: 100vh;
  background: url('https://liang-1256974191.cos.ap-beijing.myqcloud.com/mt/mt_bg1.jpg')
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
    color: #fff;
    .logo {
      @include flex(flex-start);
      img {
        width: 50px;
        height: 50px;
        margin-right: 20px;
      }
      h2 {
        font-size: 22px;
        flex: 1;
      }
    }
    .title {
      font-size: 22px;
      color: #fff;
      font-weight: 300;
    }
  }
  .body {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 0 30px;
    color: #fff;
    text-align: center;
    h1 {
      font-size: 46px;
      font-weight: bold;
      text-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
    }
    .des {
      padding-top: 20px;
      color: #fff;
      text-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
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
        margin-bottom: 15px;
        cursor: pointer;
        &:hover {
          background: #f1f1f1;
        }
        &:active {
          background: #e9e9e9;
        }
      }
      .dark-btn {
        background: rgba(255, 255, 255, 0.7);
      }
    }
  }
  .footer {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 30px;
    text-align: center;
    font-size: 14px;
    color: rgba(255, 255, 255, 0.9);
  }
  .About {
    width: 500px;
    color: #333;
    line-height: 1.6;
    p {
      text-indent: 30px;
    }
    p + p {
      margin-top: 15px;
    }
  }
}
</style>
