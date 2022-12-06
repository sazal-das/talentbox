<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="text-h6 font-weight-light">Experiencia</div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Empresa"
              outlined
              v-model="form.company"
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pr-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Lugar de trabajo"
              outlined
              v-model="form.workplace"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-select
              hide-details
              color="purple"
              v-model="form.economic"
              :items="items"
              label="Sector económico"
              outlined
            ></v-select>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pr-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Título del cargo"
              outlined
              v-model="form.jobTitle"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <v-textarea
              hide-details
              v-model="form.economic"
              color="purple"
              outlined
              name="input-7-4"
              label="Descripción"
            ></v-textarea>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pr-0'">
            <v-text-field
              hide-details
              color="purple"
              label="Rango / Jerarquía"
              outlined
              v-model="form.jobTitle"
            ></v-text-field>
            <div class="add-input mt-2">
              <div style="color: #666666;">Salario actual o último salario</div>
              <div class="mt-1">
                <v-text-field prefix="$" dense hide-details color="purple" v-model="form.place"></v-text-field>
              </div>
            </div>
            <div class="dollar-input mt-2">
              <div class="d-flex justify-space-between">
                <div style="color: #666666;">Fechas</div>
              </div>
              <v-row class="mt-1">
                <v-col cols="6" class="d-flex">
                  <span style="color: #666666;">Inicial</span>
                  <v-text-field
                    class="pl-2"
                    dense
                    prefix="Fec"
                    hide-details
                    color="purple"
                    v-model="form.minSalary"
                  ></v-text-field>
                </v-col>
                <v-divider inset vertical></v-divider>
                <v-col cols="6" class="d-flex">
                  <span style="color: #666666;">Final</span>
                  <v-text-field
                    class="pl-2"
                    dense
                    prefix="Fec"
                    hide-details
                    color="purple"
                    v-model="form.maxSalary"
                  ></v-text-field>
                </v-col>
              </v-row>
            </div>
            <div class="text-right mt-6">
              <v-btn
                large
                elevation="2"
                color="white"
                class="text-capitalize px-4 py-2 font-weight-bold"
                rounded
                @click="dialog=true"
              >
                Añadir más experiencia
                <v-icon color="purple" right dark>mdi-plus</v-icon>
              </v-btn>
            </div>
          </v-col>
        </v-row>
      </v-form>
    </div>
    <v-dialog v-model="dialog" width="600" style="border-radius: 15px">
      <v-card class="dialog-container">
        <div>
          <div class="d-flex justify-space-between">
            <div></div>
            <div>Mi experiencia</div>
            <div>
              <v-btn small icon color="purple" @click="dialog=false">
                <v-icon>mdi-close</v-icon>
              </v-btn>
            </div>
          </div>
          <div class="mt-3 inner-container">
            <div class="inner-content">
              <div class="text-right">
                <v-btn
                  style="border: 1px solid #EAEAEA; border-radius: 5px"
                  x-small
                  outlined
                  tile
                  icon
                  color="#565656"
                >
                  <v-icon>mdi-pencil</v-icon>
                </v-btn>
                <v-btn
                  style="border: 1px solid #EAEAEA; border-radius: 5px"
                  class="ml-2"
                  x-small
                  outlined
                  tile
                  icon
                  color="#565656"
                >
                  <v-icon>mdi-close</v-icon>
                </v-btn>
              </div>
              <div>Arquitecto junior</div>
              <div>AECOM</div>
              <div>Nov 2019 - Feb 2020</div>
            </div>
          </div>
        </div>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      haveJob: "yes",
      items: ["Foo", "Bar", "Fizz", "Buzz"],
      dialog: false,
      form: {
        company: "",
        workplace: "",
        economic: "",
        jobTitle: "",
        level: "",
        abilities: "",
      },
    };
  },
};
</script>

<style scoped lang="scss">
.dialog-container {
  padding: 10px;
  background-color: #faf8fb;
  border-radius: 15px;
}
.inner-container {
  padding: 10px;
  background-color: white;
  border-radius: 15px;
  height: 400px;
}
.inner-content {
  border: 1px solid #f1f1f1;
  border-radius: 10px;
  padding: 10px;
  width: 70%;
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
