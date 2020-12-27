<template>
  <div>
    <v-navigation-drawer v-model="drawer" app temporary>
      <a href="#" class="logo d-flex py-10 pl-4 align-center">
        <v-btn class="mr-4" color="primary" rounded fab depressed small>
          <span color="#fff">T</span>
        </v-btn>
        <span>Trafalgar</span>
      </a>
      <v-divider />
      <v-list>
        <v-list-item
          v-for="([icon, text, link], i) in items"
          :key="i"
          link
          @click="$vuetify.goTo(link)"
        >
          <v-list-item-icon>
            <v-icon class="pl-2">{{ icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="text-size">{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar elevate-on-scroll app height="80px" color="#fff">
      <div class="container d-flex align-center pa-0">
        <a href="#" class="logo d-flex align-center">
          <v-btn class="mr-2" color="primary" rounded fab depressed small>
            <span color="#fff">T</span>
          </v-btn>
          <span>Trafalgar</span>
        </a>
        <v-spacer />
        <v-app-bar-nav-icon
          class="mt-2"
          @click.stop="drawer = !drawer"
          v-if="isXs"
        >
        </v-app-bar-nav-icon>

        <div v-else>
          <v-list class="d-flex flex-row">
            <v-list-item
              v-for="([, text, link], i) in items"
              :key="i"
              link
              @click="$vuetify.goTo(link)"
            >
              <v-list-item-title class="text-size font-weight-regular">{{
                text
              }}</v-list-item-title>
            </v-list-item>
          </v-list>
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
      ["mdi-clipboard-search-outline", "Find a doctor", "#doctor"],
      ["mdi-approximately-equal-box", "App", "#app"],
      ["mdi-play-box-outline", "Testimonials", "#testimonials"],
      ["mdi-account-supervisor-circle", "About Us", "about"],
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
  font-weight: 500;
}
.item span {
  font-size: 18px;
  font-weight: 500;
  color: #000;
}
.text-size {
  font-size: 18px;
}
</style>
