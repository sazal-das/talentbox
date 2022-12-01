<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="text-h6 font-weight-light">Datos complementarios</div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4">
          <v-col cols="12" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Foto de perfil, sobre mi, género, medio de transporte…"
              solo
              v-model="form.residence"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-row>
              <v-col cols="9">
                <div class="add-input">
                  <div style="color: #666666;">Enlaces</div>
                  <div class="mt-1">
                    <v-text-field dense hide-details color="purple" v-model="form.place"></v-text-field>
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
            <div class="mt-4">
              <div class="chip-style">
                <v-row>
                  <v-col cols="10" class="d-flex justify-space-between">
                    <div>
                      <div class="pt-1">https://www.persona.com/cv</div>
                    </div>
                  </v-col>
                  <v-col cols="2" class="text-right">
                    <v-btn icon color="#8000c7">
                      <v-icon>fa-solid fa-xmark</v-icon>
                    </v-btn>
                  </v-col>
                </v-row>
              </div>
              <div class="chip-style mt-4">
                <v-row>
                  <v-col cols="10" class="d-flex justify-space-between">
                    <div>
                      <div class="pt-1">https://www.persona.com/po</div>
                    </div>
                  </v-col>
                  <v-col cols="2" class="text-right">
                    <v-btn icon color="#8000c7">
                      <v-icon>fa-solid fa-xmark</v-icon>
                    </v-btn>
                  </v-col>
                </v-row>
              </div>
            </div>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-row>
              <v-col cols="5">
                <div class="add-input">
                  <div style="color: #666666;">Red social</div>
                  <div class="mt-1">
                    <v-text-field dense hide-details color="purple" v-model="form.languages"></v-text-field>
                  </div>
                </div>
              </v-col>
              <v-col cols="4">
                <div class="add-input">
                  <div style="color: #666666;">Usuario</div>
                  <div class="mt-1">
                    <v-text-field dense hide-details color="purple" v-model="form.level"></v-text-field>
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
            <div class="mt-4">
              <div class="chip-style">
                <v-row>
                  <v-col cols="6" class="d-flex justify-space-between">
                    <div>
                      <div class="pt-1">Red01</div>
                    </div>
                    <v-divider class="py-2" style="padding: 0 .5px" inset vertical color="#8000c7"></v-divider>
                  </v-col>
                  <v-col cols="6" class="d-flex justify-space-between">
                    <div>
                      <div class="pt-1">Nombre usuario</div>
                    </div>
                    <v-btn icon color="#8000c7">
                      <v-icon>fa-solid fa-xmark</v-icon>
                    </v-btn>
                  </v-col>
                </v-row>
              </div>
              <div class="chip-style mt-4">
                <v-row>
                  <v-col cols="6" class="d-flex justify-space-between">
                    <div>
                      <div class="pt-1">Red02</div>
                    </div>
                    <v-divider class="py-2" style="padding: 0 .5px" inset vertical color="#8000c7"></v-divider>
                  </v-col>
                  <v-col cols="6" class="d-flex justify-space-between">
                    <div>
                      <div class="pt-1">Nombre usuario</div>
                    </div>
                    <v-btn icon color="#8000c7">
                      <v-icon>fa-solid fa-xmark</v-icon>
                    </v-btn>
                  </v-col>
                </v-row>
              </div>
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
  padding: 20px 0;
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
  padding: 5px 20px;
  font-weight: bold;
}
</style>
