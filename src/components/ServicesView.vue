<template>
  <div id="section-service" class="section-service" :style="{ backgroundColor: colors.amarelo }">
    
  </div>
</template>

<script setup>
import colors from "../assets/colors/colors";
</script>

<style scoped lang="scss">
.section-service {
  min-height: 100vh;
  display: flex;

  .service-left-section {
    width: 50%;
    padding: 40px 0 30px 100px;
    display: flex;
    flex-direction: column;
    
  }
  
  .service-right-section {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 50%;
  }
}
</style>