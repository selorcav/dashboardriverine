<template>
  <v-container class="mt-5 pa-6 pa-lg-4 pr-lg-6">
    <v-text-field
      prepend-icon="mdi-account-circle"
      label="Usuario o Correo"
      filled
    ></v-text-field>
    <v-text-field
      prepend-icon="mdi-lock"
      v-model="password"
      :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
      :rules="[rules.required, rules.min]"
      :type="show1 ? 'text' : 'password'"
      name="input-10-1"
      label="Password"
      hint="Al menos 8 caracteres"
      counter
      @click:append="show1 = !show1"
      filled
    ></v-text-field>
    <v-checkbox class="mt-0 ml-4 mb-0" label="Mantener sesión iniciada" />
    <router-link to="/dashboard">
      <v-btn color="primary" class="mb-4" block>Login</v-btn>
    </router-link>
    <a class="ml-4" href="">¿Ha olvidado su contraseña?</a>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      show1: false,
      password: "Password",
      rules: {
        required: (value) => !!value || "Required.",
        min: (v) => v.length >= 8 || "Min 8 characters",
      },
    };
  },
};
</script>

<style>
</style>