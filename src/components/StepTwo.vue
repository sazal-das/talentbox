<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="text-h6 font-weight-light">Datos generales</div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4">
          <v-col cols="12" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Correo, telefono, nombre…"
              solo
              v-model="form.email"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="large-input">
              <div style="color: #666666;">Profesión u oficio</div>
              <div class="mt-1">
                <v-text-field hide-details color="purple" v-model="form.profession"></v-text-field>
              </div>
            </div>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pr-0'">
            <div class="dollar-input">
              <div class="d-flex justify-space-between">
                <div style="color: #666666;">Expectativa salarial</div>
                <v-btn elevation="0" fab dark x-small color="grey darken-3">
                  <v-icon x-small dark>fa-solid fa-question</v-icon>
                </v-btn>
              </div>
              <v-row class="mt-1">
                <v-col cols="6" class="d-flex">
                  <span style="color: #666666;">Min</span>
                  <v-text-field
                    class="pl-2"
                    dense
                    prefix="$"
                    hide-details
                    color="purple"
                    v-model="form.minSalary"
                  ></v-text-field>
                </v-col>
                <v-divider inset vertical></v-divider>
                <v-col cols="6" class="d-flex">
                  <span style="color: #666666;">Max</span>
                  <v-text-field
                    class="pl-2"
                    dense
                    prefix="$"
                    hide-details
                    color="purple"
                    v-model="form.maxSalary"
                  ></v-text-field>
                </v-col>
              </v-row>
            </div>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-row>
              <v-col cols="9">
                <div class="add-input">
                  <div style="color: #666666;">Cargo a aplicar</div>
                  <div class="mt-1">
                    <v-text-field dense hide-details color="purple" v-model="form.charge"></v-text-field>
                  </div>
                </div>
              </v-col>
              <v-col cols="3">
                <div class="add-btn">
                  <v-btn small icon color="black">
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                </div>
              </v-col>
            </v-row>
            <div class="mt-2">
              <v-chip class="mx-1" color="#ECE4F0" close>Cargo01</v-chip>
              <v-chip class="mx-1" color="#ECE4F0" close>Cargo02</v-chip>
            </div>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-row>
              <v-col cols="9">
                <div class="add-input">
                  <div style="color: #666666;">Habilidades técnicas</div>
                  <div class="mt-1">
                    <v-text-field dense hide-details color="purple" v-model="form.abilities"></v-text-field>
                  </div>
                </div>
              </v-col>
              <v-col cols="3">
                <div class="add-btn">
                  <v-btn small icon color="black">
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                </div>
              </v-col>
            </v-row>
            <div class="mt-2">
              <v-chip class="mx-1" color="#ECE4F0" close>Habilidad01</v-chip>
              <v-chip class="mx-1" color="#ECE4F0" close>Habilidad02</v-chip>
            </div>
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
        profession: "",
        minSalary: "",
        maxSalary: "",
        charge: "",
        abilities: "",
      },
    };
  },
};
</script>

<style scoped lang="scss">
::v-deep {
  .v-text-field.v-text-field--solo:not(.v-text-field--solo-flat)
    > .v-input__control
    > .v-input__slot {
    padding: 20px 10px;
  }
  .v-input__slot::before {
    border-style: none !important;
  }
  .v-text-field.v-text-field--enclosed:not(.v-text-field--rounded)
    > .v-input__control
    > .v-input__slot,
  .v-text-field.v-text-field--enclosed .v-text-field__details {
    padding-: 20px;
  }
}
.add-input {
  padding: 8px 15px;
  border-radius: 5px;
  border: 1px solid #9e9e9e;
}
.large-input {
  padding: 20px 15px;
  border-radius: 5px;
  border: 1px solid #9e9e9e;
}
.dollar-input {
  padding: 18px 15px;
  border-radius: 5px;
  border: 1px solid #9e9e9e;
}
.add-btn {
  border: 1px dashed #9e9e9e;
  padding: 20px;
  border-radius: 5px;
}
</style>
