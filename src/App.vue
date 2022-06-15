<template>
  <div id="main">
    <MailComponentVue/>
  </div>
</template>

<script>
import MailComponentVue from './components/MailComponent.vue';

export default {
  name: 'App',

  components: {
    MailComponentVue
  },

  data: () => ({
    //
  }),
};
</script>

<style>
body{
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
#main {
  display: flex;
  justify-content: center;
  align-items: center;

  height: 100vh;
}
</style>
