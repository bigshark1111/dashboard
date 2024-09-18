<template>
  <div class="chatbox">
    <div class="messages">
      <div v-for="(msg, index) in messages" :key="index" class="message">
        {{ msg }}
      </div>
    </div>
    <input type="text" v-model="newMessage" @keyup.enter="sendMessage" placeholder="Type a message..." />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const messages = ref([]);
const newMessage = ref('');

const sendMessage = () => {
  if (newMessage.value.trim() !== '') {
    messages.value.push(newMessage.value);
    newMessage.value = '';
  }
};
</script>

<style scoped>
.chatbox {
  border: 1px solid #ccc;
  padding: 10px;
  width: 20%;
}

.messages {
  max-height: 200px;
  overflow-y: auto;
  margin-bottom: 10px;
}

.message {
  padding: 5px;
}
</style>
