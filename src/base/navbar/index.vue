<template>
  <div class="mine-navbar">
    <div class="mine-navbar-left">
      <slot name="left"></slot>
    </div>
    <!---$slots.center获取插槽名为center的插槽--->
    <div class="mine-navbar-center" v-if="$slots.center">
      <slot name="center"></slot>
    </div>
    <div class="mine-navbar-right" v-if="$slots.right">
      <slot name="right"></slot>
    </div>
    <h1 class="mine-navbar-title" v-if="title">
      <span class="mine-navbar-text" v-text="title"></span>
    </h1>
  </div>
</template>

<script>
  export default {
    name: "MeNavbar",
    props: {
      title: {
        type: String,
        default: ''
      }
    }
  };
</script>

<style scoped>
  .mine-navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 50px;
    background-color: #fff;
  }
  .mine-navbar-left {
    margin-left: 10px;
  }
  .mine-navbar-center {
    flex: 1;
    margin: 0 10px;
  }
  .mine-navbar-right {
    margin-right: 10px;
  }
  .mine-navbar-title {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 20%;
    right: 20%;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .mine-navbar-title .mine-navbar-text {
    width: 100%;
    line-height: 1.5;
    font-size: 14px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
</style>
