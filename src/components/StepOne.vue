<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="text-h6 font-weight-light">Datos generales</div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Correo electrónico"
              outlined
              v-model="form.email"
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pr-0'">
            <v-row>
              <v-col cols="3">
                <v-text-field hide-details color="purple" label="Ind." outlined v-model="form.ind"></v-text-field>
              </v-col>
              <v-col cols="9">
                <v-text-field
                  hide-details
                  color="purple"
                  label="Telefono"
                  outlined
                  v-model="form.phone"
                ></v-text-field>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Primer nombre"
              outlined
              v-model="form.firstName"
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pr-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Primer apellido"
              outlined
              v-model="form.surName"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" class="px-0">
            <v-text-field
              hide-details
              color="purple"
              label="Profesión, expectativa salarial…"
              solo
              v-model="form.profession"
            ></v-text-field>
          </v-col>
        </v-row>
      </v-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        ind: "",
        phone: "",
        firstName: "",
        surName: "",
        profession: "",
      },
    };
  },
};
</script>

<style></style>
