<template>
  <v-card class="overflow-hidden">
    <v-app-bar color="#a2362d" dark>
      <v-app-bar-nav-icon @click="showDrawer"></v-app-bar-nav-icon>

      <v-toolbar-title>{{ title }}</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>
  </v-card>
</template>

<script>
export default {
  name: "ChatHeader",

  props: {
    showDrawer: Function,
    title: {
      type: String,
      default: "聊天室"
    }
  }
};
</script>

<style></style>
