<!-- eslint-disable prettier/prettier -->
<template>
  <div class="login-form-container">
    <div class="text-subtitle-1 text-center">Iniciar sesión</div>
    <div class="inner-container">
      <div class="text-body-1 text-center">Ingresa a Talentbox</div>
      <div class="text-center">Es gratis y lo sera siempre</div>
      <div class="mt-10">
        <v-form ref="form" v-model="valid" lazy-validation>
          <v-text-field hide-details color="purple" placeholder="Correo electrónico" outlined></v-text-field>
          <v-text-field class="mt-5" hide-details color="purple" placeholder="Contraseña" outlined></v-text-field>
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
              <a class="purple--text" @click="onCLickNext()">Crear cuenta</a>
            </div>
          </div>
        </v-form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    onCLickNext() {
      this.$emit("onClickNext");
    },
  },
};
</script>

<style lang="scss" scoped>
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
</style>
