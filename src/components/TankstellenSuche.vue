<template>
  <h1>Du suchst eine Tankstelle in Köln? Nichts leichter als das!</h1>
  <h2>Wähle die Straßensuche oder lass dir die Adressen sortiert anzeigen.</h2>
  <form>
    <label for="streetsearch"></label>
    <input
      type="text"
      name="streetsearch"
      id="streetsearch"
      class="streetsearch"
      placeholder="z.B. Waldstr. "
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

input {
  border-radius: 30px 0 0 30px;
  font-family: "Poppins", sans-serif;
  font-size: 1.2rem;
}

input::placeholder {
  color: var(---honolulu-blue);
}
button {
  border-radius: 0 30px 30px 0;

  font-family: "Poppins", sans-serif;
  font-size: 1.2rem;
}

.streetsearch {
  background-color: var(---tigers-eye);
  border: none;
  color: var(---honolulu-blue);
}
button:hover {
  background-color: var(---tomato);
  cursor: pointer;
}
label {
  display: none;
}
@media (max-width: 375px) {
  form {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .streetsearch {
    border-radius: 30px;
    margin: 1rem;
  }
}
</style>
