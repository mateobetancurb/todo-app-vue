<template>
  <v-app>
    <v-container>
      <h1 class="text-center mt-5">Aplicación de tareas</h1>
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
