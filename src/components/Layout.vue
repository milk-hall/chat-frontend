<template>
  <div class="layout">
    <chat-header v-bind:showDrawer="showDrawer" />
    <layout-content>
      <slot></slot>
    </layout-content>
    <v-navigation-drawer v-model="drawer" absolute temporary height="100vh">
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="red--text text--accent-4"
        >
          <v-list-item @click="go('/chat')">
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>主页</v-list-item-title>
          </v-list-item>
          <v-list-item @click="go('/user')">
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>个人信息</v-list-item-title>
          </v-list-item>
          <v-list-item @click="go('/setting')">
            <v-list-item-icon>
              <v-icon>mdi-cog</v-icon>
            </v-list-item-icon>
            <v-list-item-title>设置</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
import ChatHeader from "./ChatHeader";
import LayoutContent from "./Content";

export default {
  components: {
    ChatHeader,
    LayoutContent
  },
  data: () => ({
    drawer: false,
    group: ["/home", "/about"]
  }),
  methods: {
    showDrawer: function() {
      this.drawer = true;
    },
    go: function(url) {
      this.$router.push(url);
    }
  }
};
</script>

<style scoped>
.layout {
  display: flex;
  flex-direction: column;
  height: 100vh;
}
</style>
