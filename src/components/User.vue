<template>
  <v-list-item class="px-3">
    <v-list-item-icon class="mb-0">
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon>
            <v-btn v-bind="attrs" v-on="on" small class="red notification" icon>
              <v-icon color="white">mdi-bell</v-icon>
            </v-btn>
            <v-icon color="white">mdi-account</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item>
            <v-list-item-title>Notificaciones</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-list-item-icon>

    <v-list-item-content class="pb-0">
      <v-list-item-title class="white--text">Usuario </v-list-item-title>
    </v-list-item-content>
  </v-list-item>
</template>

<script>
export default {};
</script>
<style lang="sass" scoped>
.notification
  position: absolute
  top: -13px
  right: -7px
  height: 20px
  width: 20px
  .mdi-bell
    font-size: 10px
</style>