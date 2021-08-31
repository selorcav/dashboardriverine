<template>
  <v-col class="pa-0 pl-2 pr-32" cols="12" md="7">
    <v-card>
      <v-card-title class="blue--text">
        {{ titulo }}
      </v-card-title>
      <v-card-text>
        <v-simple-table>
          <template>
            <tbody>
              <tr>
                <td class="d-flex align-center justify-space-between">
                  <span class="font-weight-bold">Caudal medio anual: </span>
                  <p class="mb-0">{{ caudal }}</p>
                </td>
              </tr>
              <tr>
                <td class="d-flex align-center justify-space-between">
                  <span class="font-weight-bold"
                    >Figura de la cuenca aportante:
                  </span>
                  <p class="mb-0">{{ figura }}</p>
                </td>
              </tr>
              <tr>
                <td class="d-flex align-center justify-space-between">
                  <span class="font-weight-bold">Tipo de lecho: </span>
                  <p class="mb-0">{{ lecho }}</p>
                </td>
              </tr>
              <tr>
                <td class="d-flex align-center justify-space-between">
                  <span class="font-weight-bold"
                    >Clasificación morfológica:
                  </span>
                  <p class="mb-0">{{ morfo }}</p>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-card-text>
    </v-card>
  </v-col>
</template>

<script>
export default {
  data() {
    return {
      titulo: "Rio X",
      caudal: "Caudal",
      figura: "Figura",
      lecho: "Lecho",
      morfo: "Recto",
    };
  },
};
</script>

<style>
</style>