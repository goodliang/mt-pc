<template>
  <div v-if="visible">
    <div class="modal-wrap"></div>
    <div class="modal-box">
      <div class="bg"></div>
      <div class="body">
        <div class="hd">
          <div class="tit">{{ title }}</div>
          <div class="close" @click="closed">
            <svg-icon icon-class="close" />
          </div>
        </div>
        <div class="bd">
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "modal",
  props: {
    modal: {
      type: Boolean,
      default: true
    },
    visible: {
      type: Boolean,
      default: false
    },
    title: {
      type: String,
      default: ""
    }
  },
  methods: {
    closed() {
      this.$emit("update:visible", false);
    }
  }
};
</script>

<style scoped lang="scss">
@import "../style/mixin";
.modal-wrap {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.6);
}
.modal-box {
  min-width: 200px;
  min-height: 200px;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
  z-index: 999;
  overflow: hidden;
  @include center;
  .bg {
    margin: 200px 0 0 50%;
    position: absolute;
    top: -50vh;
    left: -50vw;
    width: 100vw;
    height: 100vh;
    background: url("https://liang-1256974191.cos.ap-beijing.myqcloud.com/mt/shuiguo_bg.png")
      no-repeat bottom;
    background-size: cover;
    -webkit-filter: blur(15px);
    filter: blur(15px);
    z-index: -1;
  }
  .body {
    height: 100%;
    background: hsla(0, 0%, 100%, 0.6);
    .hd {
      padding: 10px 15px;
      @include flex();
      .close {
        font-size: 20px;
        color: #666;
        cursor: pointer;
      }
    }
    .bd {
      padding: 5px 15px 15px;
    }
  }
}
</style>
