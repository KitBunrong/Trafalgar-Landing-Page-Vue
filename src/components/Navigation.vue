<template>
  <div>
    <v-navigation-drawer v-model="drawer" app temporary>
      <v-list>
        <v-list-item-avatar></v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title class="title">Trafalgar</v-list-item-title>
        </v-list-item-content>
      </v-list>
      <v-divider />
      <v-list dense>
        <v-list-item
          v-for="([icon, text, link], i) in items"
          :key="i"
          link
          @click="$vuetify.goTo(link)"
        >
          <v-list-item-icon class="justify-center">
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="subtitle-1">{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar elevate-on-scroll app height="80px" color="#fff">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" v-if="isXs">
      </v-app-bar-nav-icon>

      <div v-else class="container d-flex pa-0 align-center">
        <a href="#" class="logo d-flex align-center">
          <v-btn
            class="logo_btn mr-3"
            color="primary"
            rounded
            fab
            depressed
            small
          >
            <span color="#fff">T</span>
          </v-btn>
          <span>Trafalgar</span>
        </a>
        <v-spacer />
        <div>
          <v-btn
            class="item text-capitalize"
            text
            @click="$vuetify.goTo('#hero')"
          >
            <span class="mr-1">Home</span>
          </v-btn>
          <v-btn
            class="item text-capitalize"
            text
            @click="$vuetify.goTo('#doctor')"
          >
            <span class="mr-1">Find a docter</span>
          </v-btn>
          <v-btn
            class="item text-capitalize"
            text
            @click="$vuetify.goTo('#app')"
          >
            <span class="mr-1">Apps</span>
          </v-btn>
          <v-btn
            class="item text-capitalize"
            text
            @click="$vuetify.goTo('#testimonial')"
          >
            <span class="mr-1">Testimonials</span>
          </v-btn>
          <v-btn
            class="item text-capitalize"
            text
            @click="$vuetify.goTo('#about')"
          >
            <span class="mr-1">About Us</span>
          </v-btn>
        </div>
      </div>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    isXs: false,
    items: [
      ["mdi-home-outline", "Home", "#hero"],
      ["mdi-home-outline", "Find a doctor", "#doctor"],
    ],
  }),
  methods: {
    onResize() {
      this.isXs = window.innerWidth < 850;
    },
  },
  watch: {
    isXs(value) {
      if (!value) {
        if (this.drawer) {
          this.drawer = false;
        }
      }
    },
  },
  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize, { passive: true });
  },
};
</script>

<style scoped>
.logo {
  font-size: 24px;
  height: 41px;
  color: #000;
  font-weight: 600;
  text-decoration: none;
}
.logo span {
  font-size: 26px;
  font-weight: 600;
}
.item span {
  font-size: 18px;
}
</style>
