<template>
  <v-app>
    <Navigation :color="color" :flat="flat" />
    <v-main>
      <Home />
      <Service />
    </v-main>
  </v-app>
</template>

<script>
import Navigation from "./components/Navigation";
import Home from "./components/HomeSection";
import Service from "./components/ServiceSection";

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
    Service,
  },
  created() {
    const top = window.pageYOffset || 0;
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
<style lang="scss">
#app {
  font-family: $body-font-family;
  overflow: hidden;

  .btn {
    text-transform: none;
    font-size: 18px;
    font-weight: 600;
    letter-spacing: 0px;

    &:hover {
      transform: scale(0.98);
    }
  }

  v-main {
    position: relative;
  }
}
</style>
