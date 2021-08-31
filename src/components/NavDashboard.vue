<template>
  <div>
    <v-navigation-drawer
      class="overflow-inherit bg-drawer"
      color="blue"
      right
      absolute
      permanent
      :mini-variant.sync="mini"
    >
      <v-btn
        @click.stop="mini = !mini"
        rounded
        height="35"
        min-width="35"
        class="toggle-btn pa-0"
        color="blue"
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

      <v-list dense nav>
        <v-dialog v-model="dialog" width="500">
          <template v-slot:activator="{ on, attrs }">
            <v-list-item
              dark
              v-bind="attrs"
              v-on="on"
              v-for="item in items"
              :key="item.title"
              link
            >
              <v-list-item-icon>
                <v-icon color="white">{{ item.icon }}</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title class="white--text">{{
                  item.title
                }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </template>

          <v-card>
            <v-card-title class="text-h5">Agregar Puente </v-card-title>
            <v-card-text>
              <v-container>
                <v-text-field label="Nombre" required></v-text-field>
                <v-text-field label="Email" required></v-text-field>
                <v-textarea
                  outlined
                  name="input-7-4"
                  label="Descripción"
                  value="Una descripción"
                ></v-textarea>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn color="red darken-1" text @click="dialog = false">
                    Cerrar
                  </v-btn>
                  <v-btn color="blue darken-1" text @click="save()">
                    Guardar
                  </v-btn>
                </v-card-actions>
              </v-container>
            </v-card-text>
          </v-card>
        </v-dialog>
      </v-list>
    </v-navigation-drawer>
    <v-snackbar class="position-absolute" color="white"  v-model="snackbar">
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
import User from "./User.vue";
export default {
  components: {
    User,
  },
  data() {
    return {
      snackbar: false,
      mini: true,
      items: [
        { title: "Agregar Empresa/Cliente", icon: "mdi-plus-circle" },
        { title: "Ver Puentes Registrados", icon: "mdi-format-list-checkbox" },
        { title: "Agregar Sensor", icon: "mdi-leak" },
        { title: "Agregar Puente", icon: "mdi-bridge" },
        { title: "Agregar Río", icon: "mdi-waves" },
      ],
      dialog: false,
    };
  },
  methods:{
    save(){
      this.dialog = false
      this.snackbar = true
    }
  }
};
</script>

<style lang="sass" scoped>
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
  z-index: 99
</style>