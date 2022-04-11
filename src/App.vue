<script setup lang="ts">
import Message from "./components/Message.vue";
import RedButton from "./components/RedButton.vue";
import { useClipboard } from "@vueuse/core"
import { ref } from "vue";

const myText = ref('')
const { copy } = useClipboard( { source: myText })

</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Message message="Hello" />
  <input type="text" v-model="myText">
  <RedButton @click="copy"> Copié ! </RedButton>
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
