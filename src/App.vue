<template>
  <v-app>
    <v-container>
      <h2 class="text-center my-5">Aplicación de tareas</h2>
      <FormularioAgregarTarea />
    </v-container>
  </v-app>
</template>

<script>
import FormularioAgregarTarea from "./components/FormularioAgregarTarea.vue";
export default {
  name: "App",
  components: {
    FormularioAgregarTarea,
  },
};
</script>
