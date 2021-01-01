<template>
  <div>
    <input class="form-control" type="text" v-model="element" />
    <p>{{ element }}</p>
    <ul class="list-group">
      <li
        v-for="(item, index) of arrayOrdenado"
        :key="item.id"
        @click="aumentar(index)"
        class="list-group-item d-flex justify-content-between align-items-center"
      >
        {{ index }} - {{ item.nombre }}
        <span v-if="item.cantidad === 0" class="badge badge-primary badge-pill">
          {{ item.cantidad }}</span
        >
        <span v-else class="badge badge-success badge-pill">
          {{ item.cantidad }}</span
        >
      </li>
      <button class="btn btn-primary btn-block" @click="reiniciar">
        Reiniciar
      </button>
    </ul>
  </div>
</template>

<script>
import { mapState, mapMutations } from "vuex";

export default {
  name: "Lista",
  computed: {
    ...mapState(["frutas"]),
    arrayOrdenado() {
      // Ordena de menor a mayor
      return this.frutas.sort((a, b) => b.cantidad - a.cantidad);
    },
  },
  methods: {
    ...mapMutations(["aumentar", "reiniciar"]),
  },
  data() {
    return {
      element: "",
    };
  },
};
</script>
 