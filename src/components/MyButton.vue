<template>
  <button @click="onClick">MyButton</button>
</template>

<script lang="ts">
import { Component, Prop, Emit, Vue } from "vue-property-decorator";

@Component
export default class MyButton extends Vue {
  // greet?のクエスチョンマークはその値が設定されないことも有りうると示唆することになります。
  // 必ず設定されることを保証する時はgreet!とエクスクラメーションマークで記述します。
  @Prop()
  public greet?: string;

  // Emit・・・親が子のイベントを監視したり、子のデータを使ったりできます。
  @Emit()
  public click() {
    // 親コンポーネントで定義している
    // 関数onMyButtonClicked()で設定されたデータを取得できる
    console.log(this.greet);
  }

  public onClick() {
    alert(this.greet);
    this.click();
  }
}
</script>
