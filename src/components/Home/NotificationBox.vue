<template>
  <div class="box box-lg">
    <div class="header">
      <box-icon name="message-rounded-detail" color="#330066" size="lg"></box-icon>
      <button class="button-primary">Archive</button>
    </div>
    <div class="inner-container scrollbar">
      <div class="spacer"></div>
      <div class="message" v-for="data in users.data" :key="data.id">
        <div class="user">
          <div class="space">
            <img :src="data.avatar" alt="User Image" class="user-icon" />
            <box-icon name="message-rounded-error" color="red" animation="tada"></box-icon>
          </div>
          <h3>{{data.first_name}} {{data.last_name}}</h3>
        </div>
        <div class="text">
          <p>{{messages}}</p>
        </div>
        <div class="icons">
          <box-icon name="check-circle" color="#28a745" animation="tada-hover"></box-icon>
          <box-icon name="x-circle" color="#ff0000" animation="tada-hover"></box-icon>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "boxicons";

export default {
  name: "NotificationBox",
  props: {
    messages: String,
    sender: String,
    users: Object
  },
  data() {
    return {
      position: "position: relative"
    };
  },
  methods: {
    mouseEnter() {
      this.position = "position: fixed";
    },
    mouseExit() {
      this.position = "position: relative";
    }
  }
};
</script>

<style scoped>
.inner-container {
  max-height: 400px;
  overflow: scroll;
  overflow-x: hidden;
}
.message {
  margin: 10px;
  padding: 10px;
  display: flex;
  justify-content: center;
  flex-direction: row;
  border-radius: 10px;
}
.message:hover {
  background-color: #f9fafd;
}
.header {
  position: sticky;
}
.text {
  width: 60%;
  text-align: justify;
  margin: 0 auto;
  align-self: flex-start;
  justify-self: flex-start;
}
.user {
  display: flex;
  flex-direction: column;
}
.space {
  display: flex;
  justify-content: center;
}
@media only screen and (max-width: 850px) {
  .text {
    text-align: left;
    max-height: 150px;
    overflow: hidden;
  }
}
@media only screen and (max-width: 600px) {
  .user-icon {
    width: 75px;
  }
}
</style>