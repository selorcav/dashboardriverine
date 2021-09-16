<template>
  <v-col class="py-0 position-relative">
    <v-dialog v-model="dialog" width="auto" content-class="ma-5 dialog-chart">
      <template v-slot:activator="{ on, attrs }">
        <v-card elevation="0">
          <v-simple-table>
            <template v-slot:default>
              <thead>
                <tr>
                  <th class="text-left">Sensores</th>
                  <th class="text-left">ID</th>
                  <th class="text-left">Pila</th>
                  <th class="text-left">Tipo</th>
                  <th class="text-left">Posición respecto a Pila</th>
                  <th class="text-left">Socavación actual</th>
                  <th class="text-left">Profundidad Remanente</th>
                  <th class="text-left">Umbral medio</th>
                  <th class="text-left">Umbral alto</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in desserts" :key="item.name">
                  <td
                    class="cursor-pointer"
                    @click="alert = !alert"
                    v-bind="attrs"
                    v-on="on"
                  >
                    {{ item.name }}
                  </td>
                  <td>{{ item.id }}</td>
                  <td>{{ item.id }}</td>
                  <td>{{ item.id }}</td>
                  <td>{{ item.id }}</td>
                  <td>{{ item.id }}</td>
                  <td>{{ item.id }}</td>
                  <td>{{ item.id }}</td>
                  <td>{{ item.id }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-card>
      </template>

      <v-card>
        <v-row class="w-inherit card-chart ma-0 pa-6">
          <v-col class="pa-0" cols="12">
            <v-sheet class="v-sheet--offset mx-auto charts" color="primary">
              <v-sparkline
                :labels="labels"
                :value="value"
                color="white"
                line-width="2"
              ></v-sparkline>
            </v-sheet>
          </v-col>
          <v-card-text class="pt-0">
            <div class="text-h6 mt-2 font-weight-light mb-2">
              Gráfico de Socavación
            </div>
            <v-divider class="my-1"></v-divider>
          </v-card-text>
          <v-col class="d-flex flex-column justify-center pa-0">
            <v-row>
              <v-col cols="6">
                <v-btn block color="primary" class="my-1">Horaria</v-btn>
              </v-col>
              <v-col cols="6">
                <v-btn block color="primary" class="my-1">Diaria</v-btn>
              </v-col>
              <v-col cols="6">
                <v-btn block color="primary" class="my-1">Mensual</v-btn>
              </v-col>
              <v-col cols="6">
                <v-btn color="primary" block class="my-1">Anual</v-btn>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-card>
    </v-dialog>
  </v-col>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
      desserts: [
        {
          name: "Sensor 1",
          id: "-",
          pila: "-",
          tipo: "-",
          posicion: "-",
          socavacion: "-",
          profundidad: "-",
          umbralM: "-",
          umbralA: "-",
        },
        {
          name: "Sensor 2",
          id: "-",
          pila: "-",
          tipo: "-",
          posicion: "-",
          socavacion: "-",
          profundidad: "-",
          umbralM: "-",
          umbralA: "-",
        },
      ],
      alert: false,
      labels: ["12", "3", "6", "9", "12", "3", "6"],
      value: [200, 675, 410, 390, 310, 460, 250],
    };
  },
  methods:{
    dialogCenter(){
      let dialog = document.getElementsByClassName("dialog-chart");
      // dialog.style.justifyContent = "center"
      console.log(dialog)
    }
  },
  mounted() {
    this.dialogCenter()
  }
};
</script>

<style lang="sass" >
@import '../assets/css/mixin'
.cursor-pointer
  cursor: pointer
.position-relative
  position: relative
.w-inherit
  width: inherit
.dialog-chart
  position: absolute
  right: 180px
  left: 180px
  +for-tablet-landscape-only
    right: 120px
    left: 120px
  +for-tablet-portrait-only
    right: 100px
    left: 100px
  +for-ipad
    position: initial
.card-chart
  +for-ipad
    width: fit-content
    background-color: white
.charts
  +for-ipad
    height: 150px
  svg
    +for-ipad
      height: 150px
</style>