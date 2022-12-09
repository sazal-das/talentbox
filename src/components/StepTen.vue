<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div class="text-h6 font-weight-light">Datos complementarios</div>
    <div class="mt-8">
      <v-form ref="form" v-model="valid" lazy-validation>
        <v-row class="pb-4">
          <v-col cols="12" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div
              @click="$emit('onClickBack')"
              v-ripple
              class="text-left elevation-2 pa-4 rounded-lg"
              style="cursor: pointer; color: #9F9F9F"
            >Foto de perfil, sobre mi, género, medio de transporte…</div>
          </v-col>
        </v-row>
        <v-row class="pb-4">
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="d-flex justify-space-between">
              <v-text-field
                hide-details
                color="purple"
                label="Enlaces"
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
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3" close>https://www.persona.com/cv</v-chip>
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3" close>https://www.persona.com/po</v-chip>
            </div>
          </v-col>
          <v-col cols="12" sm="6" :class="$vuetify.breakpoint.xs ? 'px-0' : 'pl-0'">
            <div class="d-flex justify-space-between">
              <v-text-field
                hide-details
                color="purple"
                label="Red social"
                outlined
                v-model="form.email"
              ></v-text-field>
              <v-text-field
                class="ml-3"
                hide-details
                color="purple"
                label="Usuario"
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
                <span>Red01</span>
                <span class="px-3" style="color: #8000c7">|</span>
                <span>Nombre usuario</span>
              </v-chip>
              <v-chip color="#efe9f3" class="overflow-x-auto mb-3" close>
                <span>Red02</span>
                <span class="px-3" style="color: #8000c7">|</span>
                <span>Nombre usuario</span>
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
