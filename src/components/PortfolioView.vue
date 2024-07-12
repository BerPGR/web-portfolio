<template>
  <div class="portfolio-container" :style="{ backgroundColor: colors.branco}">
    <div class="portfolio-left-section">
      <div class="experience-title">
        <p :style="{ color: colors.roxo }" class="experience">Experience</p>
        <h1 :style="{ marginTop:'16px'}">Skills & <br>Experience</h1>
      </div>
      <div class="quote-experience">
        <p :style="{ width: '80%', lineHeight:'32px'}">I'm a specialist in Mobile and Full-Stack development. A passion of mine is developing solutions and solving problems through apps and websites. Primarily on Flutter Development!</p>
      </div>

      <div class="skills-container">
        <h1 :style="{ fontWeight: '600', marginTop: '50px'}">Skills</h1>

        <div class="skills">
          <div class="skill-content" v-for="skill in skills" :key="skill.name">
            <div class="img-holder" :style="{ backgroundColor: colors.preto }">
              <img :src="skill.img" />
            </div>
            <p>{{ skill.name }}</p>
          </div>
        </div>
      </div>
      
    </div>
    <div class="portfolio-right-section">
      <div>
        <h1 class="title">Experience</h1>
      </div>

      <div class="experiences">
        <div class="experience-container" v-for="(experience, i) in experiences" :key="i">
          <div class="divider"></div>
          <div class="info-container">
            <h3 :style="{ fontSize: '16px', fontWeight: '600'}">{{experience.data}}</h3>
            <div class="info-text">
              <h2 :style="{fontSize: '26px', fontWeight: '700'}">{{experience.function}}</h2>
              <p :style="{marginTop: '20px'}">{{experience.company}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import iphoneImg from '../assets/imgs/iphone.png';
import webImg from '../assets/imgs/web.png';
import postgresqlImg from '../assets/imgs/postgresql.png';
import flutterImg from '../assets/imgs/flutter.png';
import vuejsImg from '../assets/imgs/vuejs.png';
import javaImg from '../assets/imgs/java.png';
import colors from "../assets/colors/colors";

const experiences = [
  {data: "2022 - Present", function: "Web Developer Intern", company: "CGEE"},
  {data: "2024 - 2024", function: "Mobile Developer", company: 'DSA - Divisão Sul Americana'},
  {data: "2022 - 2022", function: "Web Developer Intern", company: "Fahrenheit Marketing"},
  {data: "2021 - 2021", function: "Developer Intern", company: "Ponto Sistemas"},
]

const skills = [
  {img: flutterImg, name: "Flutter ⭐"},
  {img: vuejsImg, name: "VueJS"},
  {img: javaImg, name: "Java"},
  {img: iphoneImg, name: "Mobile Development"},
  {img: webImg, name: 'Web Development'},
  {img: postgresqlImg, name: "PostgreSQL"}
]
</script>

<style scoped lang="scss">
.portfolio-container {
  min-height: 100vh;
  display: flex;

  .portfolio-left-section {
    width: 50%;
    padding: 40px 0 30px 100px;
    display: flex;
    flex-direction: column;

    .experience-title {
      font-size: 26px;
      text-align: left;
      
      h1 {
        font-weight: 600;
      }

      .experience {
        font-size: 16px;
        transform: rotate(330deg);
        display: inline-block;
        font-weight: 600;
      }
    }

    .quote-experience {
      margin-top: 20px;
    }

    .skills-container {
      display: flex;
      flex-direction: column;
    
      h1 {
        margin-bottom: 20px;
      }
    
      .skills {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(2, auto);
        grid-gap: 20px;
        justify-items: auto;
    
        .skill-content {
          display: flex;
          flex-direction: column;
          margin-bottom: 30px;
    
          .img-holder {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 70px;
            height: 70px;
            padding: 20px;
            border-radius: 35px;
            margin-bottom: 10px;
    
            img {
              max-width: 100%;
              max-height: 100%;
            }
          }
        }
      }
    } 
  }
  
  .portfolio-right-section {
    display: flex;
    flex-direction: column;
    width: 50%;
    padding: 40px 100px 0 0;

    .title {
      font-weight: 600;
    }

    .experiences {
      display: flex;
      flex-direction: column;
      margin-top: 20px;

      .experience-container {
        display: flex;
        flex-direction: column;
        margin-top: 30px;

        .divider {
          margin-bottom: 6px;
          background-color: black;
          height: 2px;
          width: 100%;
        }

        .info-container {
          display: flex;
          justify-content: space-between;
          text-align: right;
          margin-top: 16px;

          .info-text {
            display: flex;
            flex-direction: column;
            align-self: center;
          }
        }
      }
    }
  }
}
</style>