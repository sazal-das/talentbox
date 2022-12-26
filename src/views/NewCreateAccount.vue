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
            <div v-else-if="tab===1 && tabTwoStep===1">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >¿Por qué contratar</div>
              <div :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'">con Talentbox?</div>
              <div class="mt-4">
                <div>Fusce dictum dui turpis, et faucibus magn malesuada eget. Suspendisse ut risus mauris.</div>
              </div>
            </div>
            <div v-else-if="tab===1 && tabTwoStep===2">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Publicar ofertas y</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >mantenerlas activas</div>
              <div :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'">¡Es muy fácil!</div>
            </div>
            <div v-else-if="tab===1 && tabTwoStep===3">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Encuentra perfiles más</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >compatibles con tu</div>
              <div :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'">empresa</div>
            </div>
            <div v-else-if="tab===2 && tabThreeStep===1">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >¡Publicar ofertas no</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >tiene ningún costo!</div>
            </div>
            <div v-else-if="tab===2 && tabThreeStep===2">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Los mejores talentos</div>
              <div :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'">para tu empresa</div>
            </div>
            <div v-else-if="tab===2 && tabThreeStep===3">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Encuentra perfiles más</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >compatibles con tu</div>
              <div :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'">empresa</div>
            </div>
            <div v-else-if="tab===2 && tabThreeStep===4">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >Publicar ofertas y</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >mantenerlas activas</div>
              <div :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'">¡Es muy fácil!</div>
            </div>
            <div v-else-if="tab===2 && tabThreeStep===5">
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >¡Publicar ofertas no</div>
              <div
                :class="$vuetify.breakpoint.width < 500 ? 'text-h5' : 'text-h4'"
              >tiene ningún costo!</div>
            </div>
          </div>
          <div>
            <v-img
              v-if="step===1 || step===2"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image2.png"
            ></v-img>
            <v-img
              v-else-if="(step===3 || step===4 || step===9 || step===10)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image3.png"
            ></v-img>
            <v-img
              v-else-if="(step===5 || step===6)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image4.png"
            ></v-img>
            <v-img
              v-else-if="(step===7 || step===8)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image1.png"
            ></v-img>
            <v-img
              v-else-if="(tab===1 && tabTwoStep===2)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image8.png"
            ></v-img>
            <v-img
              v-else-if="(tab===1 && tabTwoStep===3 || tabThreeStep===4)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image6.png"
            ></v-img>
            <v-img
              v-else-if="(tab===2 && tabThreeStep===1)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image7.png"
            ></v-img>
            <v-img
              v-else-if="(tab===2 && tabThreeStep===2)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/image8.png"
            ></v-img>
            <v-img
              v-else-if="(tab===2 && tabThreeStep===3 || tabThreeStep===5)"
              class="mx-auto"
              style="max-width: 500px;"
              src="/images/Captura-removeb.svg"
            ></v-img>
            <v-row
              v-else-if="tab===1 && tabTwoStep===1"
              class="mx-auto"
              style="padding-bottom: 50px"
            >
              <v-carousel
                cycle
                height="400"
                hide-delimiter-background
                style="max-width: 420px; margin: 0 auto"
                :show-arrows="false"
              >
                <v-carousel-item v-for="(item, i) in carouselImages" :key="i" :src="item.src"></v-carousel-item>
              </v-carousel>
            </v-row>
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
                @click="onClickTab(item)"
              >{{ item }}</v-tab>
            </v-tabs>
            <v-tabs-items v-model="tab">
              <v-tab-item>
                <div class="form-container">
                  <step-one v-if="step===1" @onClickNext="onClickNext()" />
                  <StepTwo v-if="step===2" @onClickBack="onClickBack()" />
                  <StepThree v-if="step===3" @onClickNext="onClickNext()" />
                  <StepFour v-if="(step===4)" @onClickBack="onClickBack()" />
                  <StepFive v-if="(step===5)" />
                  <StepSix v-if="(step===6)" />
                  <StepSeven v-if="(step===7)" />
                  <StepEight v-if="(step===8)" />
                  <StepNine v-if="(step===9)" @onClickNext="onClickNext()" />
                  <StepTen v-if="(step===10)" @onClickBack="onClickBack()" />
                </div>
              </v-tab-item>
              <v-tab-item>
                <tab-two-login-step v-if="tabTwoStep === 1" @onClickNext="onClickTabTwoNextStep()" />
                <div class="form-container">
                  <tab-two-ste-two v-if="tabTwoStep===2" @onClickNext="onClickTabTwoNextStep()" />
                  <tab-two-step-three
                    v-if="tabTwoStep===3"
                    @onClickBack="onClickTabTwoPreviousStep()"
                    @onClickNext="onClickTabTwoNextStep()"
                  />
                </div>
              </v-tab-item>
              <v-tab-item>
                <div class="form-container">
                  <tab-three-step-one
                    v-if="tabThreeStep===1"
                    @onClickNext="onClickTabThreeNextStep()"
                  />
                  <tab-three-step-two
                    v-if="tabThreeStep===2"
                    @onClickBack="onClickTabThreePreviousStep()"
                    @onClickNext="onClickTabThreeNextStep()"
                  />
                  <tab-three-step-three
                    v-if="tabThreeStep===3"
                    @onClickBack="onClickTabThreePreviousStep()"
                  />
                  <tab-three-step-four
                    v-if="tabThreeStep===4"
                    @onClickBack="onClickTabThreePreviousStep()"
                    @onClickNext="onClickTabThreeNextStep()"
                  />
                  <tab-three-step-five
                    v-if="tabThreeStep===5"
                    @onClickBack="onClickTabThreePreviousStep()"
                  />
                </div>
              </v-tab-item>
            </v-tabs-items>
            <!-- Bottom Section -->
            <!-- :style="$vuetify.breakpoint.width > 960 ? 'position: absolute; left: 40px; right: 40px; bottom: 20px;' : 'padding-bottom: 15px'" -->

            <div
              v-if="tab===0"
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
            <div
              v-if="tab===2"
              :style="$vuetify.breakpoint.width > 960 ? 'position: absolute; left: 40px; right: 40px; bottom: 20px;' : 'padding-bottom: 15px'"
              class="pt-16"
            >
              <div class="mb-8" v-if="tabThreeStep===1 || tabThreeStep===2 || tabThreeStep===3">
                <v-progress-linear
                  style="box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px; border-radius: 20px;"
                  height="15"
                  rounded
                  :color="tabThreeProgressValue===0 ? 'blue-grey lighten-5' : 'purple darken-2'"
                  :value="tabThreeProgressValue"
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
                    v-if="tabThreeStep<5"
                    @click="onClickTabThreeNextStep()"
                  >Siguiente</v-btn>
                  <div
                    v-if="tabThreeStep===1 || tabThreeStep===2 || tabThreeStep===3"
                    style="margin-top: 15px; color: #565656"
                  >Progreso de la oferta {{tabThreeProgressValue}}%</div>
                  <v-btn
                    depressed
                    rounded
                    color="purple"
                    class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                    dark
                    v-if="tabThreeStep===5"
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
                    @click="onClickTabThreePreviousStep()"
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
                  @click="onClickTabThreePreviousStep()"
                >Volver</v-btn>
                <div
                  v-if="tabThreeStep===1 || tabThreeStep===2 || tabThreeStep===3"
                  style="margin-top: 15px; color: #565656"
                >Progreso de la oferta {{tabThreeProgressValue}}%</div>
                <v-btn
                  depressed
                  rounded
                  color="purple"
                  class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                  dark
                  v-if="tabThreeStep<5"
                  @click="onClickTabThreeNextStep()"
                >Siguiente</v-btn>
                <v-btn
                  depressed
                  rounded
                  color="purple"
                  class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                  dark
                  v-if="tabThreeStep===5"
                >Guardar</v-btn>
              </div>
            </div>
            <div
              v-if="tab===1 && (tabTwoStep===2 || tabTwoStep===3)"
              :style="$vuetify.breakpoint.width > 960 ? 'position: absolute; left: 40px; right: 40px; bottom: 20px;' : 'padding-bottom: 15px'"
              class="pt-16"
            >
              <div v-if="$vuetify.breakpoint.xs" class="text-center">
                <div>
                  <v-btn
                    depressed
                    rounded
                    color="purple"
                    class="text-capitalize px-13 py-6 font-weight-bold btn-bg"
                    dark
                    v-if="tabTwoStep===2"
                    @click="onClickTabTwoNextStep()"
                  >Siguiente</v-btn>
                  <v-btn
                    depressed
                    rounded
                    color="purple"
                    class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                    dark
                    v-if="tabTwoStep===3"
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
                    @click="onClickTabTwoPreviousStep()"
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
                  @click="onClickTabTwoPreviousStep()"
                >Volver</v-btn>
                <v-btn
                  depressed
                  rounded
                  color="purple"
                  class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                  dark
                  v-if="tabTwoStep===2"
                  @click="onClickTabTwoNextStep()"
                >Siguiente</v-btn>
                <v-btn
                  depressed
                  rounded
                  color="purple"
                  class="text-capitalize px-15 py-6 font-weight-bold btn-bg"
                  dark
                  v-if="tabTwoStep===3"
                >Guardar</v-btn>
              </div>
            </div>
            <div
              v-if="tab===1 && tabTwoStep===1"
              class="text-right pt-md"
              :style="$vuetify.breakpoint.height < 800 ? '' : 'position: absolute; bottom: 20px; right: 40px;'"
            >© 2022 Talentbox</div>
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
import TabTwoLoginStep from "../components/TabTwoLoginStep.vue";
import TabTwoSteTwo from "../components/TabTwoStepTwo.vue";
import TabTwoStepThree from "../components/TabTwoStepThree.vue";
import TabThreeStepOne from "../components/TabThreeStepOne.vue";
import TabThreeStepTwo from "../components/TabThreeStepTwo.vue";
import TabThreeStepThree from "../components/TabThreeStepThree.vue";
import TabThreeStepFour from "../components/TabThreeStepFour.vue";
import TabThreeStepFive from "../components/TabThreeStepFive.vue";
import FooterSection from "../components/FooterSection.vue";
export default {
  data() {
    return {
      carouselImages: [
        {
          src: "/images/image9.png",
        },
        {
          src: "/images/image8.png",
        },
        {
          src: "/images/image6.png",
        },
      ],
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
      tabTwoStep: 1,
      tabThreeStep: 1,
      tabThreeProgressValue: 30,
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
    TabTwoLoginStep,
    TabTwoSteTwo,
    TabTwoStepThree,
    TabThreeStepOne,
    TabThreeStepTwo,
    TabThreeStepThree,
    TabThreeStepFour,
    TabThreeStepFive,
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
    onClickTab(item) {
      console.log("tab: ", this.tab);
      if (item === "Soy un talento") {
        this.step = 1;
        this.tabTwoStep = 0;
        this.tabThreeStep = 0;
        this.progressValue = 0;
        this.tabThreeProgressValue = 30;
      } else if (item === "Soy una empresa") {
        this.step = 0;
        this.tabTwoStep = 1;
        this.tabThreeStep = 0;
        this.progressValue = 0;
        this.tabThreeProgressValue = 30;
      } else if (item === "Publicar oferta") {
        this.step = 0;
        this.tabTwoStep = 0;
        this.tabThreeStep = 1;
        this.progressValue = 0;
        this.tabThreeProgressValue = 30;
      }
    },
    onClickTabTwoNextStep() {
      this.tabTwoStep = this.tabTwoStep + 1;
    },
    onClickTabTwoPreviousStep() {
      this.tabTwoStep = this.tabTwoStep - 1;
    },
    onClickTabThreeNextStep() {
      this.tabThreeStep = this.tabThreeStep + 1;
      if (this.tabThreeStep === 2) {
        this.tabThreeProgressValue = this.tabThreeProgressValue + 30;
      } else if (this.tabThreeStep === 3) {
        this.tabThreeProgressValue = this.tabThreeProgressValue + 20;
      }
    },
    onClickTabThreePreviousStep() {
      if (this.tabThreeStep !== 1) {
        this.tabThreeStep = this.tabThreeStep - 1;
        if (this.tabThreeStep === 2) {
          this.tabThreeProgressValue = this.tabThreeProgressValue - 20;
        } else if (this.tabThreeStep === 1) {
          this.tabThreeProgressValue = this.tabThreeProgressValue - 30;
        }
      }
    },
  },
};
</script>

<style scoped lang="scss">
.inner-container {
  margin-top: 10px;
  background-color: white;
  border-radius: 17px;
  padding: 40px 30px;
}
.login-form-container {
  background-color: #faf7fa;
  padding: 10px;
  max-width: 500px;
  border-radius: 17px;
  margin: 0 auto;
  margin-top: 150px;
}
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
@media only screen and (max-width: 576px) {
  .right-container {
    border-top-left-radius: 60px;
    background-color: white;
    min-height: 990px;
    padding: 20px;
    color: black;
    position: relative;
  }
}
</style>
