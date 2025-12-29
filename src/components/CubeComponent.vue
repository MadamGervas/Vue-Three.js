<template>
  <TresMesh ref="cubeRef" :position="[0, 2, 0]">
    <TresBoxGeometry :args="[1, 1, 1]" />
    <TresMeshNormalMaterial />
  </TresMesh>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { useLoop } from "@tresjs/core";

const { onBeforeRender } = useLoop();
const cubeRef = ref();

onBeforeRender(({ delta, elapsed }) => {
  if (cubeRef.value) {
    cubeRef.value.rotation.y += delta;
    cubeRef.value.rotation.z = elapsed;
  }
});
</script>
