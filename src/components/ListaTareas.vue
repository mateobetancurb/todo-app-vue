<template>
  <ul>
    <li v-for="tarea in listaTareas" :key="tarea">
      {{ tarea }}
    </li>
  </ul>
</template>

<script>
export default {
  props: ["listaTareas"],
  data() {
    return {};
  },
};
</script>
