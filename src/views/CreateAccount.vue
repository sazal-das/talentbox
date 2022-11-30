<!-- eslint-disable prettier/prettier -->
<template>
  <div class="page-container">
    <v-row no-gutters>
      <v-col style="background: white;" cols="12" sm="12" md="5">
        <div class="left-container">
          <div>
            <img style="width: 120px" src="/images/icon1.png" />
            <img style="width: 55px; margin-left: -8px" src="/images/icon2.png" />
          </div>
          <div class="header-text pl-5">
            <div
              :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
            >Imagina un asistente</div>
            <div
              :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
            >personal trabajando 24/7</div>
          </div>
          <div>
            <v-img class="mx-auto" max-width="440" src="/images/image2.png"></v-img>
          </div>
          <div style="position: absolute; bottom: 20px;">
            <v-btn icon color="white" class="mr-5">
              <v-icon>fa-brands fa-twitter</v-icon>
            </v-btn>
            <v-btn icon color="white" class="mr-5">
              <v-icon>fa-brands fa-instagram</v-icon>
            </v-btn>
            <v-btn icon color="white">
              <v-icon>fa-brands fa-facebook-f</v-icon>
            </v-btn>
          </div>
        </div>
      </v-col>
      <v-col cols="12" sm="12" md="7">
        <div class="right-container">
          <div>
            <v-tabs v-model="tab" right>
              <v-tabs-slider color="purple"></v-tabs-slider>

              <v-tab
                class="text-capitalize black--text"
                v-for="item in tabItems"
                :key="item"
              >{{ item }}</v-tab>
            </v-tabs>
            <v-tabs-items v-model="tab">
              <v-tab-item v-for="item in items" :key="item">
                <div class="form-container">
                  <step-one v-if="step===1" />
                  <StepTwo v-if="step===2" />
                  <StepThree v-if="step===3" />
                  <StepFour v-if="(step===4)" />
                  <StepFive v-if="(step===5)" />
                </div>
              </v-tab-item>
            </v-tabs-items>
          </div>
          <!-- Bottom Section -->
          <div style="position: absolute; left: 40px; right: 40px; bottom: 20px;">
            <div class="mb-8">
              <v-progress-linear
                style="box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px; border-radius: 20px;"
                height="15"
                rounded
                :color="progressValue===0 ? 'blue-grey lighten-5' : 'purple darken-2'"
                :value="progressValue"
              >
                <template v-slot:default="{ value }">
                  <span class="text-caption white--text">{{ Math.ceil(value) }}%</span>
                </template>
              </v-progress-linear>
            </div>
            <div v-if="$vuetify.breakpoint.xs" class="text-center">
              <div>
                <v-btn
                  depressed
                  rounded
                  color="purple"
                  class="text-capitalize px-13 py-6 font-weight-bold btn-bg"
                  dark
                >Siguiente</v-btn>
              </div>
              <div class="mt-4">
                <v-btn
                  depressed
                  rounded
                  outlined
                  color="purple"
                  class="text-capitalize px-16 py-6 font-weight-bold"
                  dark
                >Volver</v-btn>
              </div>
            </div>
            <div v-else class="d-flex justify-space-between" style="width: 100%">
              <v-btn
                depressed
                rounded
                outlined
                color="purple"
                class="text-capitalize px-15 py-6 font-weight-bold"
                dark
                @click="onClickBack()"
              >Volver</v-btn>
              <v-btn
                depressed
                rounded
                color="purple"
                class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                dark
                @click="onClickNext()"
              >Siguiente</v-btn>
            </div>
          </div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import StepOne from "../components/StepOne.vue";
import StepThree from "../components/StepThree.vue";
import StepTwo from "../components/StepTwo.vue";
import StepFour from "../components/StepFour.vue";
import StepFive from "../components/StepFive.vue";
export default {
  name: "CreateAccount",
  data() {
    return {
      items: [
        {
          src: "/images/image1.png",
        },
        {
          src: "/images/image2.png",
        },
        {
          src: "/images/image3.png",
        },
      ],
      tab: null,
      tabItems: ["Soy un talento", "Soy una empresa", "Publicar oferta"],
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
      valid: true,
      progressValue: 0,
      step: 1,
    };
  },
  components: {
    StepOne,
    StepThree,
    StepTwo,
    StepFour,
    StepFive,
  },
  created() {
    console.log("vuetify: ", this.$vuetify);
  },
  methods: {
    onClickBack() {
      if (this.step !== 1) {
        this.step = this.step - 1;
        this.progressValue = this.progressValue - 10;
      }
    },
    onClickNext() {
      this.step = this.step + 1;
      this.progressValue = this.progressValue + 10;
    },
  },
};
</script>

<style scoped>
.bgColor {
  background-color: #c0b4e3;
}
.font {
  font-family: "Montserrat", sans-serif;
}
.page-container {
  background-color: #c0b4e3;
  font-family: "Montserrat", sans-serif;
  height: 100vh;
  color: white;
  /* padding: 30px; */
}
.left-container {
  border-bottom-right-radius: 60px;
  background-color: #c0b4e3;
  height: 100vh;
  padding: 30px;
  position: relative;
}
.right-container {
  border-top-left-radius: 60px;
  background-color: white;
  height: 100vh;
  padding: 30px;
  color: black;
  position: relative;
}
.header-text {
  padding: 80px 0;
}
.form-container {
  padding: 10px;
  max-width: 90%;
  margin: 0 auto;
  margin-top: 80px;
}
.btn-bg {
  background-image: linear-gradient(
    to right,
    #7c00c6,
    #8400c8,
    #8d00cb,
    #9500cd,
    #9d00cf
  );
}
.inner-container {
  margin-top: 10px;
  background-color: white;
  border-radius: 17px;
  padding: 40px 30px;
}
.v-window-item .v-image {
  height: 350px !important;
  object-fit: contain !important;
  width: 350px !important;
  margin: 0 auto !important;
}
@media only screen and (max-width: 955px) {
  .left-container {
    border-bottom-right-radius: 0px;
    background-color: #c0b4e3;
    height: 100vh;
    padding: 30px;
    position: relative;
  }
}
@media only screen and (max-width: 500px) {
  .left-container {
    border-bottom-right-radius: 0px;
    background-color: #c0b4e3;
    height: 100vh;
    padding: 30px;
    position: relative;
  }
  .header-text {
    padding-top: 80px;
    padding-bottom: 80px;
  }
}
</style>
