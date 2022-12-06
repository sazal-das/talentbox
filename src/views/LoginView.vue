<!-- eslint-disable prettier/prettier -->
<template>
  <div class="page-container">
    <v-row no-gutters>
      <v-col style="background: white;" cols="12" sm="12" md="5">
        <v-container class="left-container fill-height">
          <div style="position: absolute; top: 20px">
            <img style="width: 120px" src="/images/icon1.png" />
            <img style="width: 55px; margin-left: -8px" src="/images/icon2.png" />
          </div>
          <div class="mx-auto">
            <h1 class="header-text text-center">Usar Talentbox es</h1>
            <div class="text-center text-body-1" style="padding-bottom: 40px; padding-top: 20px;">
              <div>Fusce dictum dui turpis, et faucibus magn</div>
              <div>malesuada eget. Suspendisse ut risus mauris.</div>
            </div>
          </div>
          <v-row class="mx-auto" style="padding-bottom: 50px">
            <v-carousel
              cycle
              height="400"
              hide-delimiter-background
              style="max-width: 440px; margin: 0 auto;"
              :show-arrows="false"
            >
              <v-carousel-item v-for="(item,i) in items" :key="i" :src="item.src"></v-carousel-item>
            </v-carousel>
          </v-row>
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
        </v-container>
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
                  <div class="text-subtitle-1 text-center">Iniciar sesión</div>
                  <div class="inner-container">
                    <div class="text-body-1 text-center">Ingresa a Talentbox</div>
                    <div class="text-center">Es gratis y lo sera siempre</div>
                    <div class="mt-10">
                      <v-form ref="form" v-model="valid" lazy-validation>
                        <v-text-field
                          hide-details
                          color="purple"
                          placeholder="Correo electrónico"
                          outlined
                        ></v-text-field>
                        <v-text-field
                          class="mt-5"
                          hide-details
                          color="purple"
                          placeholder="Contraseña"
                          outlined
                        ></v-text-field>
                        <div>
                          <v-btn class="mt-3 text-capitalize" text small>¿Olvido su contraseña?</v-btn>
                        </div>
                        <div class="text-center mt-6">
                          <v-btn
                            depressed
                            rounded
                            color="purple"
                            class="text-capitalize px-15 py-5 font-weight-bold btn-bg"
                            dark
                          >Ingresar</v-btn>
                        </div>
                        <div class="text-center mt-5">
                          <div>
                            ¿Nuevo en Talentbox?
                            <a
                              class="purple--text"
                              href="/create-account"
                            >Crear cuenta</a>
                          </div>
                        </div>
                      </v-form>
                    </div>
                  </div>
                </div>
              </v-tab-item>
            </v-tabs-items>
          </div>
          <div
            class="text-right"
            :style="$vuetify.breakpoint.height < 800 ? '' : 'position: absolute; bottom: 20px; right: 40px;'"
          >© 2022 Talentbox</div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "LoginPage",
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
    };
  },
  created() {
    console.log("vuetify: ", this.$vuetify);
  },
};
</script>

<style scoped lang="scss">
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
  // height: 100vh;
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
  padding: 50px 0;
}
.form-container {
  background-color: #faf7fa;
  padding: 10px;
  max-width: 500px;
  border-radius: 17px;
  margin: 0 auto;
  margin-top: 150px;
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
::v-deep {
  .v-window-item .v-image {
    height: 350px !important;
    object-fit: contain !important;
    width: 350px !important;
    margin: 0 auto !important;
  }
}
@media only screen and (max-width: 955px) {
  .left-container {
    border-bottom-right-radius: 0px;
    background-color: #c0b4e3;
    // height: 100vh;
    padding: 30px;
    position: relative;
  }
}
</style>
