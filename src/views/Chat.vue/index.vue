<template>
  <div class="chat">
    <v-container class>
      <v-row>
        <v-col sm="5" md="2" class>
          <v-card outlined style="height:100%">聊天列表</v-card>
        </v-col>
        <v-col sm="5" offset-sm="2" md="10" offset-md="0">
          <v-card outlined>
            <v-textarea />
          </v-card>

          <v-card outlined>
            <v-textarea />
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.chat {
  width: 80%;
  height: 90%;
  border-radius: 16px;
  background: #ffffff;
  opacity: 0.8;
  box-sizing: border-box;
}
</style>
