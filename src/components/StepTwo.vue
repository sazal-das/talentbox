<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="text-h6 font-weight-light">Datos generales</div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4">
          <v-col cols="12" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div
              @click="$emit('onClickBack')"
              v-ripple
              class="text-left elevation-2 pa-4 rounded-lg"
              style="cursor: pointer; color: #9F9F9F"
            >Correo, telefono, nombre…</div>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <!-- <div class="large-input">
              <div style="color: #666666;">Profesión u oficio</div>
              <div class="mt-1">
                <v-text-field hide-details color="purple" v-model="form.profession"></v-text-field>
              </div>
            </div>-->
            <v-textarea
              hide-details
              color="purple"
              label="Profesión u oficio"
              outlined
              class="input1"
              v-model="form.email"
            ></v-textarea>
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
            <div class="d-flex justify-space-between">
              <!-- <div style="width: 100%" class="add-input">
                <div style="color: #666666;">Cargo a aplicar</div>
                <div class="mt-1">
                  <v-text-field dense hide-details color="purple" v-model="form.charge"></v-text-field>
                </div>
              </div>-->
              <v-text-field
                hide-details
                color="purple"
                label="Correo electrónico"
                outlined
                v-model="form.email"
              ></v-text-field>
              <div>
                <div class="add-btn">
                  <v-btn small icon color="black">
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                </div>
              </div>
            </div>
            <div class="mt-2 d-flex">
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3 mr-1" close>Cargo01</v-chip>
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3 mr-1" close>Cargo02</v-chip>
              <!-- <div class="chip-style d-flex mr-2">
                <div class="pt-1">Cargo01</div>
                <v-btn class="ml-3 mt-1" x-small icon color="#8000c7">
                  <v-icon>fa-solid fa-xmark</v-icon>
                </v-btn>
              </div>
              <div class="chip-style d-flex mr-2">
                <div class="pt-1">Cargo02</div>
                <v-btn class="ml-3 mt-1" x-small icon color="#8000c7">
                  <v-icon>fa-solid fa-xmark</v-icon>
                </v-btn>
              </div>-->
            </div>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="d-flex justify-space-between">
              <v-text-field
                hide-details
                color="purple"
                label="Habilidades técnicas"
                outlined
                v-model="form.email"
              ></v-text-field>
              <div>
                <div class="add-btn">
                  <v-btn small icon color="black">
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                </div>
              </div>
            </div>
            <div class="mt-2 d-flex">
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3 mr-1" close>Habilidad01</v-chip>
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3 mr-1" close>Habilidad02</v-chip>
              <!-- <div class="chip-style d-flex mr-2">
                <div class="pt-1">Habilidad01</div>
                <v-btn class="ml-3 mt-1" x-small icon color="#8000c7">
                  <v-icon>fa-solid fa-xmark</v-icon>
                </v-btn>
              </div>
              <div class="chip-style d-flex mr-2">
                <div class="pt-1">Habilidad02</div>
                <v-btn class="ml-3 mt-1" x-small icon color="#8000c7">
                  <v-icon>fa-solid fa-xmark</v-icon>
                </v-btn>
              </div>-->
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
  // .input1 .v-input input:focus,
  // .v-input input {
  //   padding: 58px 4px;
  // }
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
  padding: 35px 15px;
  border-radius: 5px;
  border: 1px solid #9e9e9e;
}
.add-btn {
  border: 1px dashed #9e9e9e;
  padding: 14px;
  margin-left: 10px;
  text-align: center;
  border-radius: 5px;
}
.chip-style {
  background-color: #efe9f3;
  color: #7e7085;
  border-radius: 50px;
  padding: 5px 10px;
  font-size: 12px;
  font-weight: bold;
  width: max-content;
}
</style>
