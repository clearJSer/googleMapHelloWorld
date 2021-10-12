<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <div>这里写页面布局</div>
    <GoogleMap/>
  </div>
</template>

<script>
// @ is an alias to /src
import GoogleMap from '@/components/GoogleMap.vue'
export default {
  name: 'Home',
  components: {
    GoogleMap
  }
}
</script>
<style scoped lang="scss">
.home{
  width: 100%;
  height: 90%;
}
</style>
