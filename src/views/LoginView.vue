<!-- eslint-disable prettier/prettier -->
<template>
  <div class="page-container">
    <v-row no-gutters>
      <v-col style="background: white;" cols="12" sm="5" md="5">
        <div class="left-container">
          <div>
            <img style="width: 120px" src="/images/icon1.png" />
            <img style="width: 55px; margin-left: -8px" src="/images/icon2.png" />
          </div>
          <div>
            <h1 class="header-text text-center">Usar Talentbox es</h1>
            <div class="text-center text-body-1" style="padding-bottom: 40px; padding-top: 20px;">
              <div>Fusce dictum dui turpis, et faucibus magn</div>
              <div>malesuada eget. Suspendisse ut risus mauris.</div>
            </div>
          </div>
          <div>
            <v-carousel
              cycle
              height="400"
              hide-delimiter-background
              style="max-width: 440px; margin: 0 auto;"
              :show-arrows="false"
            >
              <v-carousel-item v-for="(item,i) in items" :key="i" :src="item.src"></v-carousel-item>
            </v-carousel>
          </div>
          <div style="position: fixed; bottom: 20px;">
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
      <v-col cols="12" sm="7" md="7">
        <div class="right-container">User Talentbox es</div>
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
    };
  },
};
</script>

<style>
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
}
.right-container {
  border-top-left-radius: 60px;
  background-color: white;
  height: 100vh;
  padding: 30px;
  color: black;
}
.header-text {
  padding: 50px 0;
}
</style>
