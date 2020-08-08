<template>
  <v-app>
    <chat-header v-bind:showDrawer="showDrawer" />
    <v-sheet
      id="scrolling-techniques-2"
      class="overflow-y-auto"
      max-height="600px"
    >
      <v-container style="height: 100vh"></v-container>
    </v-sheet>
    <v-navigation-drawer v-model="drawer" absolute temporary height="100vh">
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="red--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Account</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
import ChatHeader from "./components/ChatHeader";

export default {
  name: "App",

  components: {
    ChatHeader
  },

  data: () => ({
    drawer: false,
    group: ['/home','/about']
  }),
  methods:{
    showDrawer:function(){
      this.drawer=true
    }
  }
};
</script>
