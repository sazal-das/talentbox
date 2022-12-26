<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="d-flex justify-space-between">
      <div class="text-h6 font-weight-light">Nueva oferta</div>
    </div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4 mt-3">
          <v-col cols="12" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div
              @click="$emit('onClickBack')"
              v-ripple
              class="text-left elevation-2 pa-4 rounded-lg"
              style="cursor: pointer; color: #9F9F9F"
            >Habilidades del talento</div>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="pl-3 pb-4">¿Estas buscando practicas?</div>
            <div class="d-flex">
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
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="pl-3 pb-4">Género</div>
            <div class="d-flex">
              <div
                class="mr-2"
                style="cursor: pointer;"
                :class="gender==='female' ? 'yes-or-no-active' : 'yes-or-no'"
                @click="gender='female'"
              >Femenino</div>
              <div
                class="ml-2"
                style="cursor: pointer;"
                :class="gender==='male' ? 'yes-or-no-active' : 'yes-or-no'"
                @click="gender='male'"
              >Masculino</div>
              <div
                class="ml-2"
                style="cursor: pointer;"
                :class="gender==='other' ? 'yes-or-no-active' : 'yes-or-no'"
                @click="gender='other'"
              >Otro</div>
            </div>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="pb-4 pt-2">
              <div class="pl-3">Medio de transporte</div>
              <div class="d-flex mt-3">
                <div
                  :class="transport==='taxi' ? 'active-transport' : 'transport'"
                  @click="transport='taxi'"
                >
                  <i class="fa-solid fa-taxi fa-lg"></i>
                </div>
                <div
                  :class="transport==='bus' ? 'active-transport' : 'transport'"
                  @click="transport='bus'"
                >
                  <i class="fa-solid fa-bus fa-lg"></i>
                </div>
                <div
                  :class="transport==='bicycle' ? 'active-transport' : 'transport'"
                  @click="transport='bicycle'"
                >
                  <i class="fa-solid fa-bicycle fa-lg"></i>
                </div>
                <div
                  :class="transport==='motorcycle' ? 'active-transport' : 'transport'"
                  @click="transport='motorcycle'"
                >
                  <i class="fa-solid fa-motorcycle fa-lg"></i>
                </div>
                <div
                  :class="transport==='walk' ? 'active-transport' : 'transport'"
                  @click="transport='walk'"
                >
                  <i class="fa-solid fa-person-walking fa-lg"></i>
                </div>
              </div>
            </div>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="dollar-input mt-2">
              <div class="d-flex justify-space-between">
                <div style="color: #666666;">Vigencia de la oferta</div>
              </div>
              <v-row class="mt-1">
                <v-col cols="6" class="d-flex">
                  <span style="color: #666666;">Fecha</span>
                  <v-text-field
                    class="pl-2"
                    dense
                    hide-details
                    color="purple"
                    v-model="form.minSalary"
                  ></v-text-field>
                </v-col>
                <v-divider inset vertical></v-divider>
                <v-col cols="6" class="d-flex">
                  <span style="color: #666666;">Fecha</span>
                  <v-text-field
                    class="pl-2"
                    dense
                    hide-details
                    color="purple"
                    v-model="form.maxSalary"
                  ></v-text-field>
                </v-col>
              </v-row>
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
      items: ["Foo", "Bar", "Fizz", "Buzz"],
      form: {
        academicLevel: "",
        obtainedTitle: "",
        institution: "",
        metodología: "",
        initial: "",
        final: "",
      },
      gender: "",
      transport: "taxi",
    };
  },
};
</script>

<style scoped lang="scss">
.transport {
  border-radius: 8px;
  background-color: #fefefe;
  width: 60px;
  text-align: center;
  padding: 18px 0;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  margin-right: 25px;
  color: #838383;
  cursor: pointer;
}
.active-transport {
  border-radius: 8px;
  background-color: #8000c7;
  width: 60px;
  text-align: center;
  padding: 18px 0;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  margin-right: 25px;
  color: white;
  cursor: pointer;
}
.user {
  border: 1px solid #c5c3c3;
  border-radius: 10px;
  text-align: center;
  padding: 35px 0;
  cursor: pointer;
}
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
