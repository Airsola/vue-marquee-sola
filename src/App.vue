<template>
  <div id="app">
    <mt-cloud-header :userName="name" @logout="handlerLogout"></mt-cloud-header>
    <!--<div style="height: 800px;" ></div>-->
  </div>
</template>

<script>
import MtCloudHeader from './MtCloudHeader.vue'

export default {
  name: 'app',
  components: {
    MtCloudHeader
  },
  data() {
    return {
      name: "SolaZhou-7777777777"
    }
  },
  methods: {
    handlerLogout() {
      console.log("退出登录")
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  background-color: gray;
  height: 300px;
}

</style>
