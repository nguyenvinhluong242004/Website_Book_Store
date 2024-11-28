<template>
  <button class="btnChat" @click="chatClick">
    <i class="fa-brands fa-facebook-messenger"></i>
    <div class="chatBox" v-if="chatBoxVisible" @click.stop="doSth">
      <div class="chatBoxHeader">Hỗ Trợ Khách Hàng</div>
      <div class="chatContent">
        <p>Hello! How can I assist you today?</p>
      </div>
      <textarea class="chatInput" placeholder="Type your message..."></textarea>
    </div>
  </button>
</template>

<script>
export default {
  name: "ChatBox",
  data() {
    return {
      chatBoxVisible: false,
    };
  },
  methods: {
    chatClick() {
      // Ẩn hiện chatbox ấn nút
      if (this.chatBoxVisible === false) {
        this.chatBoxVisible = true;
      } else {
        this.chatBoxVisible = false;
      }
    },
  },
};
</script>

<style>
.btnChat {
  position: fixed;
  bottom: 10px;
  right: 10px;
  width: 40px;
  height: 38px;
  z-index: 1000;
  border: none;
  border-radius: 100px;

  display: flex;
  justify-content: center;
  align-items: center;

  background: linear-gradient(to bottom, rgb(13, 215, 255), rgb(47, 16, 247));

  color: white;
  font-size: 25px;
}
.chatBox {
  position: fixed;
  bottom: 10px;
  right: 60px;

  width: 300px;
  height: 400px;
  background-color: white;
  
  border: 1px solid #ccc;
  border-radius: 10px;
  
  z-index: 1000;

  flex-direction: column;

  font-size: 20px;
}
.chatBoxHeader {
  background: white;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  color: rgb(13, 141, 247);
  padding: 10px;
  border-radius: 10px 10px 0 0;
  font-weight: bold;
  display: flex;
  justify-content: center;
  align-items: center;
}
/* Nội dung chat */
.chatContent {
  padding: 10px;
  overflow-y: auto;
  flex-grow: 1;
}
/* Input chat */
.chatInput {
  width: 100%;
  padding: 10px;
  border: none;
  border-top: 1px solid #ccc;
  border-radius: 0 0 10px 10px;
  resize: none;
}
</style>