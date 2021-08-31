<template>
  <v-col class="pa-0 pl-2 pr-32 table-data-info" cols="12" md="7" offset-md="5">
    <v-card>
      <v-simple-table class="over-scroll">
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
              <td class="cursor-pointer" @click="alert = !alert">
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
    <v-alert
      :value="alert"
      transition="scale-transition"
      class="ma-0 pa-0 mt-4"
    >
      <v-card>
        <v-row>
          <v-col cols="9">
            <v-sheet
              class="v-sheet--offset mx-auto"
              color="primary"
              max-width="calc(100% - 32px)"
            >
              <v-sparkline
                :labels="labels"
                :value="value"
                color="white"
                line-width="2"
                padding="16"
              ></v-sparkline>
            </v-sheet>
          </v-col>
          <v-col class="d-flex flex-column justify-center pr-10">
            <v-btn color="primary" class="my-1 d-block">Horaria</v-btn>
            <v-btn color="primary" class="my-1 d-block">Diaria</v-btn>
            <v-btn color="primary" class="my-1 d-block">Mensual</v-btn>
            <v-btn color="primary" class="my-1 d-block">Anual</v-btn>

          </v-col>
        </v-row>

        <v-card-text class="pt-0">
          <div class="text-h6 mt-2 font-weight-light mb-2">
            Gráfico de Socavación
          </div>
          <v-divider class="my-2"></v-divider>
        </v-card-text>
      </v-card>
    </v-alert>
  </v-col>
</template>

<script>
export default {
  data() {
    return {
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
      labels: ["12", "3", "6", "9", "12", "3", "6", "9"],
      value: [200, 675, 410, 390, 310, 460, 250, 240],
    };
  },
};
</script>

<style lang="sass" scoped>
.pr-32
  padding-right: 72px !important
.over-scroll
  overflow: scroll
.table-data-info
  margin-top: -70px
.cursor-pointer
  cursor: pointer
</style>