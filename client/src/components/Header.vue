<template>
  <div>
  <a-affix :offset-top="top">
    <a-menu mode="horizontal" theme="dark" class="header_bg">
      <a-menu-item key="home" @click="handleToHomePage()"> <a-icon type="home" />Home</a-menu-item>
      <a-menu-item key="resume" @click="handleToResumePage()"> <a-icon type="smile" />Resume</a-menu-item>
      <a-menu-item key="contact"> <a-icon type="contacts" />Contact</a-menu-item>
      <a-menu-item key="situation"> <a-icon type="heat-map" />Situation</a-menu-item>
      <a-menu-item key="setting"> <a-icon type="setting" />Setting</a-menu-item>
    </a-menu>
    </a-affix>
  </div>
</template>

<script>
export default {
  name: 'Header',
  methods:{
    handleToHomePage(){ window.location.href = '/'},
    handleToResumePage(){ window.location.href = '/resume'}
  }
}
</script>

<style scoped src="@/components/Header.css">

</style>
