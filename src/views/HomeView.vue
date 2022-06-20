<script lang="ts" setup>
import { ref } from "vue";
import { useElementHover } from "@vueuse/core";
import { EIpcName } from "@/types";
const ele = ref();
const isHovered = useElementHover(ele);

function onMouseEnter(e: any) {
  if (window.api.setIgnoreMouse) {
    window.api.setIgnoreMouse(false);
  }
}
function onMouseLeave(e: any) {
  if (window.api.setIgnoreMouse) {
    window.api.setIgnoreMouse(true, { forward: true });
  }
}
</script>
<template>
  <div class="home"
       ref="ele"
       @mouseenter="onMouseEnter"
       @mouseleave="onMouseLeave">
    {{ isHovered }}
  </div>
</template>


<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100px;
  background-color: #42b983;
}
</style>