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
                <v-tooltip
                  bottom
                  color="white"
                  class="black--text"
                  style="box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px; opacity: 0%;"
                >
                  <template v-slot:activator="{ on, attrs }">
                    <v-btn x-small icon color="#535353" v-bind="attrs" v-on="on">
                      <v-icon>fa-solid fa-circle-question fa-xl</v-icon>
                    </v-btn>
                  </template>
                  <div
                    class="black--text pa-4 rounded-lg"
                    style="box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px; width: 450px;"
                  >
                    <div
                      class="text-center font-weight-bold"
                    >Salario promedio en tu profesion u oficio</div>
                    <apexchart type="bar" height="350" :options="chartOptions" :series="series"></apexchart>
                  </div>
                </v-tooltip>
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
            </div>
          </v-col>
        </v-row>
      </v-form>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import VueApexCharts from "vue-apexcharts";
Vue.use(VueApexCharts);
// eslint-disable-next-line vue/multi-word-component-names
Vue.component("apexchart", VueApexCharts);
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
      series: [
        {
          data: [5, 10, 15, 20, 18, 25, 15, 5, 3],
        },
      ],
      chartOptions: {
        chart: {
          height: 350,
          type: "bar",
        },
        colors: [
          "#CAB8E5",
          "#CAB8E5",
          "#CAB8E5",
          "#CAB8E5",
          "#8B10D2",
          "#CAB8E5",
          "#CAB8E5",
          "#CAB8E5",
          "#CAB8E5",
        ],
        plotOptions: {
          bar: {
            columnWidth: "25%",
            distributed: true,
          },
        },
        dataLabels: {
          enabled: false,
        },
        legend: {
          show: false,
        },
        xaxis: {
          categories: [
            "$2,000,000",
            "",
            "",
            "",
            "$5,000,000",
            "",
            "",
            "",
            "$10,000,000",
          ],
          labels: {
            style: {
              colors: "black",
              fontSize: "12px",
            },
          },
        },
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
