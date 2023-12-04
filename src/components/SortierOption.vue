<template>
  <div>
    <button v-on:click="sort">A-Z</button>
    <button v-on:click="sortReverse">Z-A</button>
  </div>
</template>

<script>
export default {
  name: "SortierOption",
  props: { gasstations: Array },
  data() {
    return {
      newStreet: "",
    };
  },
  computed: {},
  methods: {
    sort() {
      console.log(this.newStreet);
    },
  },
};
</script>

<style scoped>
* {
  padding-top: 2rem;
}
button {
  border-radius: 25%;
  margin: 10px;
  padding: 1.5rem;
  color: var(---honolulu-blue);
  background-color: var(---tigers-eye);
  outline: none;
  border: none;
  opacity: 0.9;
  font-family: "Poppins", sans-serif;
  font-size: 1.2rem;
}
button:hover {
  background-color: var(---tomato);
  cursor: pointer;
}
</style>
