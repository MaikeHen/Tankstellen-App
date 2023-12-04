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
  methods: {},
};
</script>

<style scoped>
* {
  padding: 2rem;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
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
}
button:hover {
  background-color: var(---tomato);
  cursor: pointer;
}
</style>
