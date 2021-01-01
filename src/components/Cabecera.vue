<template>
  <div class="text-center">
    <h1>Frut List</h1>
    <input class="form-control" type="text" v-model="element" />
    <p>{{ element }}</p>
  </div>
</template>

<script>
export default {
  name: "Cabecera",
  data() {
    return {
      element: "",
    };
  },
};
</script>