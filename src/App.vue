<template>
  <nav><router-link to="/"></router-link></nav>
  <router-view />
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Outfit:wght@400;700&family=Poppins:wght@300&display=swap");
:root {
  ---argentinian-blue: #57b8ff;
  ---honululu-blue: #2176ae;
  ---tigers-eye: #b66d0d;
  --hyunyadi-yellow: #fbb13c;
  ---tomato: #fe6847;
}

* {
  margin: 0;
  box-sizing: border-box;
}
#app {
  margin: 0;
  padding: 3rem;
  font-family: "Poppins", sans-serif;
  text-align: center;
  background-color: var(--hyunyadi-yellow);
  color: var(---honululu-blue);
}
</style>
