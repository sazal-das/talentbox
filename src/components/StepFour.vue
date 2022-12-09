<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="text-h6 font-weight-light">Datos personales</div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4">
          <v-col cols="12" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div
              @click="$emit('onClickBack')"
              v-ripple
              class="text-left elevation-2 pa-4 rounded-lg"
              style="cursor: pointer; color: #9F9F9F"
            >Residencia, documento, fecha nacimiento, estado civil…</div>
          </v-col>
        </v-row>
        <div class="text-body-1 mt-4">¿Tiene empleo actualmente?</div>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="mt-5 d-flex">
              <div
                class="mr-2"
                style="cursor: pointer;"
                :class="haveJob==='no' ? 'yes-or-no-active' : 'yes-or-no'"
                @click="haveJob='no'"
              >Si</div>
              <div
                class="ml-2"
                style="cursor: pointer;"
                :class="haveJob==='yes' ? 'yes-or-no-active' : 'yes-or-no'"
                @click="haveJob='yes'"
              >No</div>
            </div>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'px-0'">
            <div class="large-input">
              <div class="d-flex justify-space-between">
                <div class="d-flex">
                  <div style="color: #666666;">Permiso de trabajo</div>
                  <div class="ml-5">
                    <v-tooltip
                      bottom
                      color="white"
                      class="black--text"
                      style="box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;"
                    >
                      <template v-slot:activator="{ on, attrs }">
                        <v-btn x-small icon color="#535353" v-bind="attrs" v-on="on">
                          <v-icon>fa-solid fa-circle-exclamation fa-lg</v-icon>
                        </v-btn>
                      </template>
                      <div
                        class="black--text pa-4 rounded-lg"
                        style="box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;"
                      >
                        <div>Donec sem sapien, fermentum a</div>
                        <div>consequat vitae, iaculis ut quam.</div>
                        <div>Aliquam faucibus, ligula at aliquet</div>
                        <div>ultrices, magna tortor feugiat dolor,</div>vel laoreet nisi ligula sed ante.
                      </div>
                    </v-tooltip>
                  </div>
                </div>
                <div>
                  <v-checkbox dense input-value="true" value></v-checkbox>
                </div>
              </div>
            </div>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="d-flex justify-space-between">
              <!-- <div class="add-input">
                <div style="color: #666666;">Lugar de las ofertas</div>
                <div class="mt-1">
                  <v-text-field dense hide-details color="purple" v-model="form.place"></v-text-field>
                </div>
              </div>-->
              <v-text-field
                hide-details
                color="purple"
                label="Lugar de las ofertas"
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
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3 mr-1" close>Lugar01</v-chip>
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3" close>Lugar02</v-chip>
              <!-- <div class="chip-style d-flex mr-2">
                <div class="pt-1">Lugar01</div>
                <v-btn class="ml-3 mt-1" x-small icon color="#8000c7">
                  <v-icon>fa-solid fa-xmark</v-icon>
                </v-btn>
              </div>
              <div class="chip-style d-flex mr-2">
                <div class="pt-1">Lugar02</div>
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
                label="Idiomas"
                outlined
                v-model="form.email"
              ></v-text-field>
              <v-text-field
                class="ml-4"
                hide-details
                color="purple"
                label="Nivel"
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
            <div class="mt-4">
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3" close>
                <span>Idioma01</span>
                <span class="px-3" style="color: #8000c7">|</span>
                <span>B1</span>
              </v-chip>
              <br />
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3" close>
                <span>Idioma01</span>
                <span class="px-3" style="color: #8000c7">|</span>
                <span>A1</span>
              </v-chip>
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
      haveJob: "yes",
      form: {
        residence: "",
        workPermit: false,
        place: "",
        languages: "",
        level: "",
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
  padding: 14px;
  margin-left: 10px;
  text-align: center;
  border-radius: 5px;
}
.yes-or-no-active {
  padding: 10px;
  border-radius: 50px;
  border: 2px solid #8000c7;
  width: 130px;
  text-align: center;
  color: #8000c7;
  font-weight: bold;
}
.yes-or-no {
  padding: 10px;
  border-radius: 50px;
  border: 2px solid #9e9e9e;
  width: 130px;
  text-align: center;
  color: black;
  font-weight: bold;
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
