<template>
  <div id="section-service" class="service-container" :style="{ backgroundColor: colors.amarelo }">
    <i class="fa-solid fa-chevron-left icon" @click="scrollBack"/>
  </div>
</template>

<script setup>
import colors from "../assets/colors/colors";
</script>

<style scoped lang="scss">
.service-container {
    min-height: 100vh;
    position: relative;

    .icon {
      position: absolute;
      padding: 30px;
      height: 20px;
      cursor: pointer
    }
}
</style>