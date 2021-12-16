<template>
  <div class="app_bg">
    <Header/>
    <router-view/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style scoped src="@/App.css">
</style>
