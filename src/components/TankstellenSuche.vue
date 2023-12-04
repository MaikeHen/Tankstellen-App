<template>
  <p>Du suchst eine Tankstelle in Köln? Nichts leichter als das!</p>
  <form>
    <label for="streetsearch"></label>
    <input
      type="text"
      name="streetsearch"
      id="streetsearch"
      class="streetsearch"
      placeholder="z.B. Volksgartenstraße"
      v-model="newStreet"
    />
    <button class="streetsearch" type="submit" @click.prevent="streetSearch">
      Suchen
    </button>
  </form>
</template>

<script>
export default {
  name: "TankstellenSuche",
  emits: ["StreetSearchInput"],
  props: { gasstations: Array },
  data() {
    return {
      newStreet: "",
    };
  },
  methods: {
    streetSearch() {
      this.$emit("StreetSearchInput");
    },
  },
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

input {
  border-radius: 30px 0 0 30px;
}

input::placeholder {
  color: var(---text-color-button);
}
button {
  border-radius: 0 30px 30px 0;
}
.streetsearch {
  background-color: var(---tigers-eye);
  border: none;
  opacity: 0.9;
  color: var(---honolulu-blue);
}
button:hover {
  background-color: var(---tomato);
  cursor: pointer;
}

label {
  display: none;
}
</style>
