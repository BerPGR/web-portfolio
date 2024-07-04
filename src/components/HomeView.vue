<template>
  <div class="home-container" :style="{ backgroundColor: colors.branco }">
    <div class="home-section">
      <div class="home-left-section">

        <div>
          <h1>I am</h1>
          <h1>Your</h1>
          <h1 class="current-word">{{currentWord}}</h1>
        </div>

        <div class="home-buttons">
          <button :style="{ backgroundColor: colors.roxo, color: colors.branco }" class="button-chat">Let's Talks <i class="fa-regular fa-paper-plane" /></button>
          <button :style="{ backgroundColor: colors.branco }" class="button-portfolio">Portfolio <i class="fa-solid fa-arrow-trend-up" /></button>
        </div>

        <div class="social-media">
          <i class="fa-brands fa-instagram"/>
          <i class="fa-brands fa-linkedin-in"/>
          <i class="fa-brands fa-github"/>
        </div>
      </div>
      <div class="home-right-section">

      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "vue";
import colors from "../assets/colors/colors";

const iam = ['Mobile Developer', 'Web Devepoler', 'Full-Stack Developer']
let currentWord = ref(iam[0])
let wordIndex = 0

const changeWord = () => {
  wordIndex = (wordIndex + 1) % iam.length
  currentWord.value = iam[wordIndex]
}

let intervalId: number;

onMounted(() => {
  intervalId = window.setInterval(changeWord, 6000)
})

onUnmounted(() => {
  clearInterval(intervalId)
})
</script>

<style scoped lang='scss'>
.home-container {
  min-height: 100vh;

    .home-section {
      display: flex;
      height: calc(100vh - 80px);

      .home-left-section {
        background-color: red;
        width: 50%;
        padding: 10px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-content: center;

        .social-media {
          display: flex;
          justify-content: space-between;
          align-items: center;
        }

        .current-word {
          animation: fadeInOut 6s infinite;
        }

        .home-buttons {
          display: block;

          .button-chat { 
            cursor: pointer;
            padding: 20px;
            border: none;
            border-radius: 15px;
            font-size: 16px;
            font-weight: 500;
          }

          .button-portfolio {
            cursor: pointer;
            padding: 20px;
            border: none;
            border-radius: 15px;
            margin-left: 12px;
            font-size: 16px;
            font-weight: 500;
          }
        }
      }

      .home-right-section {
        width: 50%;
      }
    }

  @keyframes fadeInOut {
    0% {
      opacity: 0;
    }
    50% {
      opacity: 1
    }
    100% {
      opacity: 0
    }
  }
}
</style>