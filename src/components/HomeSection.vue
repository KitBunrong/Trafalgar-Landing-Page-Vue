<template>
  <v-container id="home">
    <div class="d-none d-lg-block">
      <img
        class="home-bg-top"
        src="@/assets/img/Screen Shot 2020-12-09 at 15.40.54.png"
        alt=""
      />
    </div>
    <v-row>
      <div class="align-self-md-center col-sm-6 col-12">
        <h1 class="home-title mb-2">
          Virtual healthcare<br />
          for you
        </h1>
        <p class="home-text mb-8">
          Trafalgar provides progressive, and affordable healthcare, accessible
          on mobile and online for everyone
        </p>
        <v-btn
          class="btn primary"
          text
          rounded
          depressed
          large
          @click="$vuetify.goTo('#service')"
        >
          <span>Consult today</span>
        </v-btn>
      </div>
      <div class="align-self-center text-right col-sm-6 col-12">
        <img
          src="@/assets/img/trafalgar-header illustration 1.png"
          alt=""
          class="home-img"
        />
      </div>
    </v-row>
  </v-container>
</template>

<script>
export default {};
</script>

<style lang="scss">
#home {
  margin-top: 40px;

  .home-bg-top {
    position: absolute;
    left: -45px;
    top: 40px;
  }

  .home-title {
    font-size: 48px;
    font-weight: 700;
  }
  .home-text {
    font-size: 21px;
    font-weight: 300;
    max-width: 450px;
  }
  .home-img {
    width: 100%;
    height: auto;
  }
}
// *== If [device] is less than or equal to 960px
@media only screen and (max-width: 960px) {
  #home {
    padding: 20px 30px 0;
  }
}
</style>
