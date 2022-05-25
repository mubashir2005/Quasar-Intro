<template>
  <div class="wrapper">
    {{registered ? (
    <div class="homeWrapper">
      <div class="main"></div>
    </div>
    ): (
    <div class="singupContainer"></div>
    )}}
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>
