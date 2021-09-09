<template>
  <div class="z-999">
    <v-navigation-drawer
      class="overflow-inherit bg-drawer"
      color="blue"
      right
      absolute
      permanent
      :mini-variant.sync="mini"
      width="280"
    >
      <v-btn
        @click.stop="mini = !mini"
        rounded
        height="35"
        min-width="35"
        class="pa-0 ms-3 mt-2"
        color="blue"
        elevation="0"
      >
        <v-icon color="white">
          {{ mini ? "mdi-chevron-left" : "mdi-chevron-right" }}
        </v-icon>
      </v-btn>
      <v-list>
        <v-list-item>
          <v-list-item-content class="pb-0">
            <v-btn icon :class="mini ? 'd-block' : 'd-none'">
              <v-img height="30" width="10" src="../assets/logo-icon.png" />
            </v-btn>
            <v-img
              height="60"
              :class="mini ? 'd-none' : 'd-block'"
              src="../assets/riverin-logo-bl.png"
            ></v-img>
          </v-list-item-content>
        </v-list-item>
        <User />
      </v-list>

      <v-divider></v-divider>

      <add-bridge />
      <add-client />
      <add-sensor />
      <add-river />
      <bridge-list />
      <bridge-list-2 />


    </v-navigation-drawer>
    <v-snackbar class="position-absolute" color="white" v-model="snackbar">
      <span class="blue--text">Puente agregado</span>
      <template v-slot:action="{ attrs }">
        <v-btn color="blue" v-bind="attrs" @click="snackbar = false">
          Cerrar
        </v-btn>
      </template>
    </v-snackbar>
  </div>
</template>

<script>
import AddBridge from './NavMenu/AddBridge.vue';
import AddClient from './NavMenu/AddClient.vue';
import AddRiver from './NavMenu/AddRiver.vue';
import AddSensor from './NavMenu/AddSensor.vue';
import BridgeList from './NavMenu/BridgeList.vue';
import BridgeList2 from './NavMenu/BridgeList2.vue';
import User from "./User.vue";
export default {
  components: {
    User,
    AddBridge,
    AddClient,
    AddSensor,
    AddRiver,
    BridgeList,
    BridgeList2,
  },
  data() {
    return {
      snackbar: false,
      mini: true,
      items: [
        { title: "Ver Puentes Registrados", icon: "mdi-format-list-checkbox" },
      ],
      
    };
  },
  methods: {
    save() {
      this.snackbar = true;
    },
  },
};
</script>

<style lang="sass">
.overflow-inherit
  overflow: inherit
.toggle-btn
  position: absolute
  left: -35px
  top: 0
  z-index: 3
.bg-drawer
  background-image: url('../assets/bg-drawer.jpg')
  background-size: cover
  background-repeat: no-repeat
  z-index: 5 !important

</style>