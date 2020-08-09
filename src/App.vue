<template>
  <v-app>
    <basicLayout>
      <router-view/>
    </basicLayout>
  </v-app>
</template>

<script>
import basicLayout from "./components/Layout";
export default {
  name: "App",

  components: {
    basicLayout
  }
};
</script>
