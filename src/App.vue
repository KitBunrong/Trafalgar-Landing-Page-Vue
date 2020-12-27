<template>
  <v-app>
    <Navigation :color="color" :flat="flat" />
    <v-main>
      <Home />
    </v-main>
  </v-app>
</template>

<script>
import Navigation from "./components/Navigation";
import Home from "./components/HomeSection";
export default {
  name: "App",
  data: () => ({
    fab: null,
    color: "",
    flat: null,
  }),
  components: {
    Navigation,
    Home,
  },
  created() {
    const top = windowYOffset || 0;
    if (top <= 60) {
      this.color = "transparent";
      this.flat = true;
    }
  },
  watch: {
    fab(value) {
      if (value) {
        this.color = "secondary";
        this.flat = false;
      } else {
        this.color = "transparent";
        this.flat = true;
      }
    },
  },
  method: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 60;
    },
    goTop() {
      this.$vuetify.goTop(0);
    },
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Mulish:wght@500&display=swap");
#app {
  font-family: "Mulish", sans-serif;
}
</style>
