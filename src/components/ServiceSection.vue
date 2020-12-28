<template>
  <v-container id="service">
    <div class="d-none d-lg-block">
      <img class="service-bg-left" src="@/assets/img/Vector1.png" alt="" />
    </div>
    <div class="d-none d-lg-block">
      <img src="@/assets/img/element 1.svg" alt="" class="service-bg-right" />
    </div>
    <h1 class="service-title text-center">Our service</h1>
    <hr
      style="margin: 15px auto 30px; width: 55px; border: 2px solid black; border-radius: 5px; background-color: black;"
    />
    <p class="service-desc">
      We provide to you the best choiches for you. Adjust it to your health
      needs and make sure your undergo treatment with our highly qualified
      doctors you can consult with us which type of service is suitable for your
      health
    </p>
    <v-row class="mt-8">
      <div
        v-for="(service, i) in services"
        :key="i"
        class="cols-12 col-sm-6 col-md-4"
      >
        <v-card class="card">
          <div class="card-icon">
            <img :src="require(`../assets/img/${service.icon}`)" alt="" />
          </div>
          <div class="card-title">{{ service.title }}</div>
          <div class="card-desc">{{ service.desc }}</div>
        </v-card>
      </div>
    </v-row>
    <div class="service-btn">
      <v-btn class="btn primary--text" rounded depressed outlined large>
        <span>Learn more</span>
      </v-btn>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      services: [
        {
          icon: "Frame.png",
          title: "Search doctor",
          desc:
            "Choose your doctor from thousands of specialist, general, and trusted hospitals",
        },
        {
          icon: "Group.png",
          title: "Online pharmacy",
          desc:
            "Buy  your medicines with our mobile application with a simple delivery system",
        },
        {
          icon: "Frame (1).png",
          title: "Consultation",
          desc:
            "Free consultation with our trusted doctors and get the best recomendations",
        },
        {
          icon: "Frame (3).png",
          title: "Details info",
          desc:
            "Free consultation with our trusted doctors and get the best recomendations",
        },
        {
          icon: "Frame (2).png",
          title: "Emergency care",
          desc:
            "You can get 24/7 urgent care for yourself or your children and yourlovely family",
        },
        {
          icon: "Group (2).png",
          title: "Tracking",
          desc: "Track and save your medical history and health data ",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#service {
  margin-top: 100px;

  .service-bg-left {
    position: absolute;
    left: 0px;
    top: 825px;
  }

  .service-bg-right {
    position: absolute;
    right: 120px;
    top: 1146px;
  }

  .service-desc {
    max-width: 950px;
    text-align: center;
    z-index: 100;
    font-size: 18px;
    margin: 0 auto 20px;
  }

  .card {
    border-radius: 20px;
    box-shadow: 10px 40px 50px rgba(229, 233, 246, 0.4);
    min-height: 350px;
    padding: 40px 30px;
    transition: all 0.4s ease-in-out;

    &:hover {
      box-shadow: 15px 45px 55px rgba(115, 138, 214, 0.4);
      transform: scale(1.03);
    }

    .card-icon {
      img {
        height: 100px;
        width: 78px;
      }
    }

    .card-title {
      font-size: 24px;
      font-weight: 700;
      padding-top: 20px;
    }

    .card-desc {
      font-size: 16px;
      font-weight: 300;
      padding-top: 15px;
    }
  }

  .service-btn {
    margin-top: 64px;
    text-align: center;
  }
}
@media only screen and (max-width: 1264px) {
  #service {
    .service-desc {
      max-width: 750px;
    }
  }
}

@media only screen and (max-width: 960px) {
  #service {
    .service-desc {
      max-width: 650px;
    }

    .card {
      margin: auto;
      max-width: 380px;
      padding-left: 55px;
    }
  }
}
</style>
