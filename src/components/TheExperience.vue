<script setup lang="ts">
import CubeComponent from "./CubeComponent.vue";
</script>

<template>
  <TresCanvas clear-color="#FFC0CB" window-size>
    <TresPerspectiveCamera
      :args="[75, 1, 0.1, 1000]"
      :position="[3, 1, 4]"
      :look-at="[0, 0, 0]"
    />

    <TresScene>
      <CubeComponent />
    </TresScene>
    <TresAxesHelper />
  </TresCanvas>
</template>
