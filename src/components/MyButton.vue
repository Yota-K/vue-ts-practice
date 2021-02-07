<template>
  <button @click="onClick">MyButton</button>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class MyButton extends Vue {
  // greet?のクエスチョンマークはその値が設定されないことも有りうると示唆することになります。
  // 必ず設定されることを保証する時はgreet!とエクスクラメーションマークで記述します。
  @Prop()
  public greet?: string;

  public onClick() {
    alert(this.greet);
  }
}
</script>
