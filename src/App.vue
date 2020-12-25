<template>
  <v-app>
    <v-main>
      <Navigation />
    </v-main>
  </v-app>
</template>

<script>
import Navigation from "./components/Navigation";
export default {
  name: "App",
  components: {
    Navigation,
  },

  data: () => ({}),
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Mulish:wght@500&display=swap");
#app {
  font-family: "Mulish", sans-serif;
}
btn span {
  font-size: 18px;
}
</style>
