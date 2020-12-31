<template>
  <v-container id="healthcare">
    <v-row>
      <v-col cols="12" sm="6" class="align-self-center pr-sm-4">
        <img
          class="healthcare-img"
          src="@/assets/img/trafalgar-illustration sec02 1.png"
          alt=""
        />
      </v-col>
      <v-col cols="12" sm="6" class="healthcare-info pl-md-16 pl-sm-5">
        <h1>
          Leading healthcare <br />
          providers
        </h1>
        <hr class="underline" />
        <p class="healthcare-desc">
          Trafalgar provides progressive, and affordable healthcare, accessible
          on mobile and online for everyone. To us, it’s not just work. We take
          pride in the solutions we deliver
        </p>
        <v-btn class="btn primary--text px-7 mt-4" rounded large outlined>
          Learn more
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {};
</script>

<style lang="scss">
#healthcare {
  margin-top: 100px;

  .healthcare-img {
    width: 100%;
    height: auto;
  }

  .healthcare-info {
    margin-top: 64px;
  }
}

@media only screen and (max-width: 600px) {
  #healthcare {
    .healthcare-img {
      padding: 30px;
    }

    .healthcare-info {
      text-align: center;
      margin-top: 0px;

      .underline {
        margin: 10px auto;
      }

      .healthcare-desc {
        max-width: 420px;
        margin: auto;
      }
    }
  }
}
</style>
