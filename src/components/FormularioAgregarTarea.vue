<template>
  <v-form
    @submit.prevent="guardarTarea"
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="tarea"
      :rules="tareaRules"
      label="Escribe aquí tu tarea..."
      required
    />
    <div class="mt-5">
      <v-btn
        :disabled="!valid"
        color="success"
        class="mr-4"
        @click.prevent="validate"
      >
        Guardar
      </v-btn>
      <v-btn color="error" class="mr-4" @click="reset"> Resetear </v-btn>
    </div>
  </v-form>
  <listaTareas :listaTareas="listaTareas" />
</template>
<script>
import ListaTareas from "./ListaTareas.vue";
export default {
  components: {
    ListaTareas,
  },
  data: () => ({
    valid: true,
    tarea: "",
    listaTareas: [],
    tareaRules: [
      (v) => !!v || "Tarea es obligatoria",
      (v) => (v && v.length > 4) || "La tarea debe tener más de 4 caracteres",
    ],
  }),

  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.guardarTarea();
      }
      return;
    },
    reset() {
      this.$refs.form.reset();
    },
    guardarTarea() {
      this.listaTareas.push(this.tarea);
      this.tarea = "";
      this.reset();
    },
  },
};
</script>
