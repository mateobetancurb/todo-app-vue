<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <v-text-field
      v-model="name"
      :rules="tareaRules"
      label="Escribe aquí tu tarea..."
      required
    />
    <div class="mt-5">
      <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
        Guardar
      </v-btn>
      <v-btn color="error" class="mr-4" @click="reset"> Resetear </v-btn>
    </div>
  </v-form>
</template>
<script>
export default {
  data: () => ({
    valid: true,
    name: "",
    tareaRules: [
      (v) => !!v || "Tarea es obligatoria",
      (v) => (v && v.length > 4) || "La tarea debe tener más de 4 caracteres",
    ],
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
  },
};
</script>
