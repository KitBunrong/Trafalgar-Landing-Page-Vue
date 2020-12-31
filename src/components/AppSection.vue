<template>
  <v-container id="app">
    <v-row>
      <v-col cols="12" sm="6" class="app-info">
        <h1>
          Download our <br />
          mobile apps
        </h1>
        <hr class="underline" />
        <p class="app-desc">
          Our dedicated patient engagement app and web portal allow you to
          access information instantaneously (no tedeous form, long calls, or
          administrative hassle) and securely
        </p>
        <v-btn class="btn primary--text mt-6" rounded outlined large
          >Download <v-icon>mdi-arrow-down</v-icon></v-btn
        >
      </v-col>
      <v-col cols="12" sm="6" class="align-self-center">
        <img
          class="app-img"
          src="@/assets/img/trafalgar-illustration sec03 1.png"
          alt=""
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {};
</script>

<style lang="scss">
#app {
  margin-top: 100px;

  .app-img {
    width: 100%;
    height: auto;
  }

  .app-info {
    margin-top: 50px;
    // text-align: center;

    .app-desc {
      max-width: 500px;
    }
  }
}

@media only screen and (max-width: 600px) {
  #app {
    .app-img {
      padding: 30px;
    }
    .app-info {
      text-align: center;
      .underline {
        margin: 10px auto;
      }
    }
  }
}
</style>
