<template>
  <hello-world class="font" />
</template>

<script>
import HelloWorld from "../components/HelloWorld";

export default {
  name: "HomeView",

  components: {
    HelloWorld,
  },
};
</script>
<style>
.font {
  font-family: "Montserrat", sans-serif;
}
</style>
