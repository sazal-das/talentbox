<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="page-container">
      <v-row style="background: white">
        <v-col class="left-container" cols="12" sm="12" md="5">
          <!-- Header Logo -->
          <div>
            <img style="width: 120px" src="/images/icon1.png" />
            <img style="width: 55px; margin-left: -8px" src="/images/icon2.png" />
          </div>
          <!-- Text content -->
          <div class="header-text pl-5">
            <div v-if="(step===1 || step===2)">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Imagina un asistente</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >personal trabajando 24/7</div>
            </div>
            <div v-else-if="(step===3 || step===4 || step===9 || step===10)">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Déjanos ayudarte a</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >encontrar el trabajo</div>
            </div>
            <div v-else-if="(step===5 || step===6)">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Ordenamos tu perfil</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >tomando en cuenta</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >habilidades técnicas</div>
            </div>
            <div v-else-if="(step===7 || step===8)">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >¡Encuentra tu trabajo</div>
              <div :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'">soñado!</div>
            </div>
          </div>
          <div>
            <v-img
              v-if="step===1 || step===2"
              class="mx-auto"
              max-width="440"
              src="/images/image2.png"
            ></v-img>
            <v-img
              v-else-if="(step===3 || step===4 || step===9 || step===10)"
              class="mx-auto"
              max-width="440"
              src="/images/image3.png"
            ></v-img>
            <v-img
              v-else-if="(step===5 || step===6)"
              class="mx-auto"
              max-width="440"
              src="/images/image4.png"
            ></v-img>
            <v-img
              v-else-if="(step===7 || step===8)"
              class="mx-auto"
              max-width="440"
              src="/images/image1.png"
            ></v-img>
          </div>
          <div style="padding-top: 40px; position: absolute; bottom: 20px;">
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
        </v-col>
        <v-col style="background: #c0b4e3" cols="12" sm="12" md="7" class="pa-0">
          <div class="right-container">
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
                  <StepSix v-if="(step===6)" />
                  <StepSeven v-if="(step===7)" />
                  <StepEight v-if="(step===8)" />
                  <StepNine v-if="(step===9)" />
                  <StepTen v-if="(step===10)" />
                </div>
              </v-tab-item>
            </v-tabs-items>
            <!-- Bottom Section -->
            <!-- :style="$vuetify.breakpoint.width > 960 ? 'position: absolute; left: 40px; right: 40px; bottom: 20px;' : 'padding-bottom: 15px'" -->
            <div
              :style="$vuetify.breakpoint.width > 960 ? 'position: absolute; left: 40px; right: 40px; bottom: 20px;' : 'padding-bottom: 15px'"
              class="pt-16"
            >
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
                    v-if="step<10"
                    @click="onClickNext()"
                  >Siguiente</v-btn>
                  <div
                    v-if="(step>1)"
                    style="margin-top: 15px; color: #565656"
                  >Probabilidad de match con ofertas {{progressValue}}%</div>
                  <v-btn
                    depressed
                    rounded
                    color="purple"
                    class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                    dark
                    v-if="step===10"
                  >Guardar</v-btn>
                </div>
                <div class="mt-4">
                  <v-btn
                    depressed
                    rounded
                    outlined
                    color="purple"
                    class="text-capitalize px-16 py-6 font-weight-bold"
                    dark
                    @click="onClickBack()"
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
                <div
                  v-if="(step>1)"
                  style="margin-top: 15px; color: #565656"
                >Probabilidad de match con ofertas {{progressValue}}%</div>
                <v-btn
                  depressed
                  rounded
                  color="purple"
                  class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                  dark
                  v-if="step<10"
                  @click="onClickNext()"
                >Siguiente</v-btn>
                <v-btn
                  depressed
                  rounded
                  color="purple"
                  class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                  dark
                  v-if="step===10"
                >Guardar</v-btn>
              </div>
            </div>
          </div>
        </v-col>
      </v-row>
    </div>
    <FooterSection class="mt-3" />
  </div>
</template>

<script>
import StepOne from "../components/StepOne.vue";
import StepThree from "../components/StepThree.vue";
import StepTwo from "../components/StepTwo.vue";
import StepFour from "../components/StepFour.vue";
import StepFive from "../components/StepFive.vue";
import StepSix from "../components/StepSix.vue";
import StepSeven from "../components/StepSeven.vue";
import StepEight from "../components/StepEight.vue";
import StepNine from "../components/StepNine.vue";
import StepTen from "../components/StepTen.vue";
import FooterSection from "../components/FooterSection.vue";
export default {
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
    StepSeven,
    StepSix,
    StepEight,
    StepNine,
    StepTen,
    FooterSection,
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

<style scoped lang="scss">
.font {
  font-family: "Montserrat", sans-serif;
}
.page-container {
  background-color: #c0b4e3;
  font-family: "Montserrat", sans-serif;
  //   height: 100vh;
  color: white;
}
.left-container {
  border-bottom-right-radius: 60px;
  background-color: #c0b4e3;
  min-height: 950px;
  padding: 30px;
  position: relative;
}
.header-text {
  padding: 80px 0;
}
.right-container {
  border-top-left-radius: 60px;
  background-color: white;
  min-height: 990px;
  padding: 60px;
  color: black;
  position: relative;
}
.form-container {
  padding: 10px;
  margin-bottom: 50px;
  max-width: 90%;
  margin: 0 auto;
  margin-top: 80px;
}
</style>
