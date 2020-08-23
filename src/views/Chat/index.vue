<template>
  <div class="chat">
    <v-container>
      <v-row>
        <v-col sm="5" md="3">
          <v-card>
            <div style="height:70vh;overflow-y:auto">
              <v-list three-line>
                <template v-for="(item, index) in items">
                  <v-subheader
                    v-if="item.header"
                    :key="item.header"
                    v-text="item.header"
                  ></v-subheader>

                  <v-divider
                    v-else-if="item.divider"
                    :key="index"
                    :inset="item.inset"
                  ></v-divider>

                  <v-list-item v-else :key="item.title" @click="sendMessage">
                    <v-list-item-avatar>
                      <v-img :src="item.avatar"></v-img>
                    </v-list-item-avatar>

                    <v-list-item-content>
                      <v-list-item-title
                        v-html="item.title"
                      ></v-list-item-title>
                      <v-list-item-subtitle
                        v-html="item.subtitle"
                      ></v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </template>
              </v-list>
            </div>
          </v-card>
        </v-col>
        <v-col sm="5" offset-sm="2" md="9" offset-md="0">
          <v-card>
            <chat-message />
          </v-card>
          <v-card>
            <v-textarea
              outlined
              no-resize
              height="10vh"
              maxlength="150"
              counter
              v-model="txMessage"
            />
            <div class="my-2 sent">
              <v-btn color="primary" @click="sendMessage">发送</v-btn>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import ChatMessage from "./ChatMessage";

export default {
  components: {
    ChatMessage
  },
  data: () => ({
    items: [
      { header: "Today" },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
        title: "Brunch this weekend?",
        subtitle:
          "<span class='text--primary'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?"
      },
      { divider: true, inset: true },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
        title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
        subtitle:
          "<span class='text--primary'>to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend."
      },
      { divider: true, inset: true },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
        title: "Oui oui",
        subtitle:
          "<span class='text--primary'>Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?"
      },
      { divider: true, inset: true },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/4.jpg",
        title: "Birthday gift",
        subtitle:
          "<span class='text--primary'>Trevor Hansen</span> &mdash; Have any ideas about what we should get Heidi for her birthday?"
      },
      { divider: true, inset: true },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/5.jpg",
        title: "Recipe to try",
        subtitle:
          "<span class='text--primary'>Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos."
      }
    ],
    txMessage: ""
  }),
  methods: {
    sendMessage: function(){
      console.log(this.txMessage);
    },
  }
};
</script>

<style scoped>
.chat {
  width: 80%;
  height: 90%;
  border-radius: 16px;
  background: #ffffff;
  opacity: 0.9;
  box-sizing: border-box;
}
.sent {
  text-align: right;
  padding-bottom: 24px;
  padding-right: 16px;
}
</style>
