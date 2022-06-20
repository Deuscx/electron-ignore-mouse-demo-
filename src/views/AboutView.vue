<script lang="ts" setup>
import { ref } from "vue";
import { useElementHover } from "@vueuse/core";
const ele = ref();
const isHovered = useElementHover(ele);
</script>
<template>
  <div class="home"
       ref="ele">
    {{ isHovered }}
  </div>
</template>


<style lang="scss" scoped>
.home {
  width: 100vw;
  height: 100vh;
}
</style>