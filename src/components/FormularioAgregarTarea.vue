<template>
  <v-form class="mt-10">
    <v-text-field label="Agrega tu tarea" v-model="tarea" />
    <v-btn :disabled="disabledBtn">Guardar</v-btn>
  </v-form>
</template>

<script>
export default {
  name: "FormularioAgregarTarea",
  data() {
    return {
      tarea: "",
      disabledBtn: true,
    };
  },
};
</script>
