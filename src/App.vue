<script lang="ts">
import { defineComponent } from "vue";
import Message from "./components/Message.vue";

export default defineComponent({
  components: {
    Message

  }
})
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Message message="Hello" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
