<template>
  <v-app>
    <router-view />
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
<style lang="sass">


.main-content
  .v-alert
    background-color: transparent !important
  .v-alert__wrapper
    display: inherit
</style>
