<template>
  <div id="app">
    <router-view v-if="isRouterAlive"/>
  </div>
</template>
<script>
export default {
  name: 'App',
  data(){
    return {
      isRouterAlive: true
    }
  },
  provide() {
    return {
      reload: this.reload
    }
  },
  methods: {
    reload() {
      this.isRouterAlive = false
      console.log(11)
      this.$nextTick(() => {
        this.isRouterAlive = true
      })
    }
  },
}
</script>
<style lang="scss">
</style>
