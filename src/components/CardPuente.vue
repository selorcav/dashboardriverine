<template>
  <v-col class="pb-0">
    <v-card elevation="0" max-width="500" v-for="item in puentes" :key="item.id">
      <v-carousel
        :continuous="false"
        :cycle="cycle"
        :show-arrows="true"
        hide-delimiter-background
        delimiter-icon="mdi-minus"
        height="200"
      >
        <v-carousel-item v-for="img in item.img" :key="img.id">
          <v-img :src="img" />
        </v-carousel-item>
      </v-carousel>
      <v-card-title class="blue--text">
        {{ item.nombre }}
      </v-card-title>
      <v-card-text>
        <v-row>
          <v-col class="pa-0 px-1" cols="6">
            <v-simple-table>
              <template>
                <tbody>
                  <tr>
                    <td>
                      <span class="font-weight-bold">Ubicación:</span>
                      {{ item.ubicacion }}
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <span class="font-weight-bold">Nº de Pilas</span>
                      {{ item.numPilas }}
                    </td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
          </v-col>
          <v-col class="pa-0 px-1" cols="6">
            <v-simple-table>
              <template>
                <tbody>
                  <tr>
                    <td>
                      <span class="font-weight-bold"
                        >Profundidad de las fundaciones</span
                      >
                      {{ item.profundidad }}
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <span class="font-weight-bold">Largo del puente:</span>
                      {{ item.largo }}
                    </td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
          </v-col>
        </v-row>
      </v-card-text>
    </v-card>
  </v-col>
</template>

<script>
export default {
  data() {
    return {
      puentes: [
        {
          nombre: "Puente A",
          ubicacion: ["-X", "-Y"],
          numPilas: 6,
          profundidad: "profundidad",
          largo: 300 + "mt",
          img: [
            "https://i.imgur.com/f656uB3.jpg",
            "https://i.imgur.com/b6cSGqm.jpg",
          ],
        },
      ],
      cycle: false,
    };
  },
};
</script>
<style lang="sass" scoped>
.pr-32
  padding-right: 72px !important
</style>