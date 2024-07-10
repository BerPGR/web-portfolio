<template>
  <div class="home-container" :style="{ backgroundColor: colors.branco }">
    <div class="home-section">
      <div class="home-left-section">

        <div>
          <div :style="{paddingBottom: '30px', width: '100%'}" class="iam-title">
            <p class="hello" :style="{ color: colors.roxo }">Hello!</p>
            <h1>I am</h1>
            <h1>Your</h1>
            <h1 class="current-word">{{currentWord}}</h1>
          </div>
  
          <p>Hi! I'm a Web/Mobile/Fullstack developer - creating awesome
            <br>apps and websites for companies around the world!
          </p>
  
          <div class="home-buttons">
            <button :style="{ backgroundColor: colors.roxo, color: colors.branco }" class="button-chat">Let's Talks <i class="fa-regular fa-paper-plane" /></button>
            <button :style="{ backgroundColor: colors.branco }" class="button-portfolio">Portfolio <i class="fa-solid fa-arrow-trend-up" /></button>
          </div>
        </div>

        <div class="social-media" :style="{ marginTop: '50px'}">
          <span>Check out my</span>
          <a v-for="(social, i) in socialMedia" :key="i" :href="social.link" target="blank" :style="{color: 'black'}">
            <i :class="social.class" style="height: 30px; cursor: pointer"/>
          </a>
          
        </div>
      </div>
      <div class="home-right-section">
          <p class="name" :style="{ color: colors.roxo }">Bernardo, A.K.A, Benny</p>
          <img src="../assets/imgs/otter.jpg" class="otter-img"/>
          <q :style="{marginTop: '20px'}">That's my favorite animal, btw</q>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "vue";
import colors from "../assets/colors/colors";
import { transform } from "typescript";

const iam = ['Mobile Developer', 'Web Developer', 'Full-Stack Developer']
const socialMedia = [
  {
    link: "https://www.instagram.com/be_polaco/",
    class: "fa-brands fa-instagram"
  },
  {
    link: "https://www.linkedin.com/in/bernardomm27/",
    class: "fa-brands fa-linkedin-in"
  },
  {
    link: "https://github.com/BerPGR",
    class: "fa-brands fa-github"
  },
]

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
    .home-section {
      display: flex;
      height: calc(100vh - 80px);

      .home-left-section {
        width: 50%;
        padding: 40px 0 30px 100px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        
        .iam-title {
          font-size: 28px;
          text-align: left;
          
          h1 {
            font-weight: 600;
          }

          .hello {
            font-size: 16px;
            transform: rotate(325deg);
            display: inline-block;
            font-weight: 600;
          }
        }

        .social-media {
          max-width: 70%;
          display: flex;
          justify-content: space-between;
          align-items: center;
        }

        .current-word {
          animation: fadeInOut 6s infinite;
        }

        .home-buttons {
          display: block;
          margin-top: 60px;

          .button-chat { 
            cursor: pointer;
            padding: 20px;
            border: none;
            border-radius: 20px;
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
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 50%;

        .name {
          transform: rotate(333deg);
          padding: 0 220px 20px 0;
          font-size: 20px;
          font-weight: 600;
        }

        .otter-img {
          width: 60%;
          object-fit: contain;
          clip-path: polygon(50% 0%, 90% 20%, 100% 60%, 75% 100%, 25% 100%, 0% 60%, 10% 20%);
        }
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