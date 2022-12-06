<!-- eslint-disable prettier/prettier -->
<template>
  <div class="footer-container">
    <v-container>
      <v-row>
        <v-col cols="4" sm="5" md="2" class="text-center">
          <img src="/images/servicio-de-empleo-color.png" />
        </v-col>
        <v-col
          cols="8"
          sm="7"
          md="6"
          class="text-center"
          style="color: #999999"
        >Vinculado a la red de prestadores del Servicio Público de Empleo. Autorizado por la Unidad Administrativa</v-col>
        <v-col cols="6" sm="6" md="2" class="text-center">
          <img src="/images/innpulsa.png" />
        </v-col>
        <v-col cols="6" sm="6" md="2" class="text-center">
          <img src="/images/school-for-startups.png" />
        </v-col>
      </v-row>
      <div class="footer-links mt-4">
        <a>Precios</a>
        <v-divider inset vertical></v-divider>
        <a>Quienes somos</a>
        <v-divider inset vertical></v-divider>
        <a>Preguntas frecuentes</a>
        <v-divider inset vertical></v-divider>
        <a>Aviso legal y condiciones</a>
        <v-divider inset vertical></v-divider>
        <a>Contáctanos</a>
        <v-divider inset vertical></v-divider>
        <a>Política de privacidad</a>
      </div>
    </v-container>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.footer-container {
  padding: 20px 0;
  background-color: #f7f6f8;
}
.footer-links {
  display: flex;
  flex-wrap: wrap;
  color: #999999;
  justify-content: space-around;
}
a {
  color: #999999 !important;
}
</style>
