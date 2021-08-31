<template>
  <v-row>
    <card-puente />
    <card-rio />
    <card-sensor />
  </v-row>
</template>

<script>
import CardPuente from "./CardPuente.vue";
import CardRio from "./CardRio.vue";
import CardSensor from "./CardSensor.vue";
export default {
  components: { CardPuente, CardRio, CardSensor },
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
</style>