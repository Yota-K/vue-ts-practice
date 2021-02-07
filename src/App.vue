<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
    <h2>{{ greetText }}</h2>
    <MyButton :greet="greetText" @click="onMyButtonClicked" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue";
import MyButton from "@/components/MyButton.vue";

@Component({
  components: {
    HelloWorld,
    MyButton
  }
})
export default class Home extends Vue {
  public greetText = "初期データ";

  public onMyButtonClicked() {
    this.greetText = "こんにちは";
  }
}
</script>

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
