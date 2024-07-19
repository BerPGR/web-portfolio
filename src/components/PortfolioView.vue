<template>
  <div class="portfolio-container" :style="{ backgroundColor: colors.branco}">
    <div class="portfolio-left-section">
      <div class="experience-title">
        <p :style="{ color: colors.roxo }" class="experience">Experience</p>
        <h1>Skills & <br>Experience</h1>
        <p class="quote-text">I'm a specialist in Mobile and Full-Stack development. A passion of mine is developing solutions and solving problems through apps and websites. Primarily on Flutter Development!</p>
      </div>

      <div class="skills-container">
        <h1 :style="{ fontWeight: '600', marginTop: '50px'}">Skills</h1>

        <div class="skills">
          <div class="skill-content" v-for="skill in skills" :key="skill.name">
            <div class="img-holder" :style="{ backgroundColor: colors.preto }">
              <img :src="skill.img" />
            </div>
            <p class="skill-text">{{ skill.name }}</p>
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
            <div class="info-text">
              <div class="info-upper-data">
                <h3 :style="{ fontSize: '16px', fontWeight: '600'}">{{experience.data}}</h3>
                <h2 :style="{fontSize: '26px', fontWeight: '700'}" class="info-text-function">{{experience.function}}</h2>
              </div>
              <div class="info-down-data">
                <p class="info-text-location">{{experience.location}}</p>
                <p class="info-text-company">{{experience.company}}</p>
              </div>

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
  {data: "2022 - Present", function: "Web Developer Intern", company: "CGEE",  location: 'Brasília, BR'},
  {data: "2024", function: "Mobile Developer", company: 'DSA - Divisão Sul Americana',  location: 'Brasília, BR'},
  {data: "2022", function: "Web Developer Intern", company: "Fahrenheit Marketing", location: 'Texas, USA'},
  {data: "2021", function: "Developer Intern", company: "Ponto Sistemas", location: 'Joinville, BR'},
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
$breakpoint-xs: 576px;
$breakpoint-sm: 768px;
$breakpoint-md: 992px;
$breakpoint-lg: 1200px;
$breakpoint-xl: 1400px;

.portfolio-container {
  min-height: 100vh;
  display: flex;
  
  @media screen and (max-width: $breakpoint-md){
    flex-direction: column;
    align-items: center;
    padding: 40px 0;
  }

  .portfolio-left-section {
    width: 50%;
    padding: 40px 0 30px 100px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    @media screen and (max-width: $breakpoint-md){
      padding: 0;
      width: 80%;
    }  

    .experience-title {
      @media screen and (max-width: $breakpoint-md){
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
       }

      h1 {
        font-weight: 700;
        font-size: 52px;
        margin-top: 16px;

        @media screen and (max-width: $breakpoint-md){
          text-align: center;
          margin-top: 0;
          font-size: 36px;
        } 
      }

      .experience {
        font-size: 16px;
        transform: rotate(330deg);
        display: inline-block;
        font-weight: 600;

        @media screen and (max-width: $breakpoint-md){
          text-align: center;
          transform: rotate(0deg);
          display: flex;
          font-size: 24px;
          font-weight: bold;
        }
      }
      .quote-text {
        width: 80%;
        line-height: 32px;
        margin-top: 16px;

        @media screen and (max-width: $breakpoint-md){
          text-align: center;
          width: 100%;
        }
      }
    }

    .skills-container {
      display: flex;
      flex-direction: column;

      @media screen and (max-width: $breakpoint-md){
        align-items: center;
      }
    
      h1 {
        margin-bottom: 20px;
      }
    
      .skills {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(2, 1fr);
        grid-gap: 20px;
        justify-items: auto;

        @media screen and (max-width: $breakpoint-xs){
          justify-items: center;
          grid-template-columns: repeat(2, 1fr);
          grid-template-rows: repeat(3, 1fr);
        }
    
        .skill-content {
          display: flex;
          flex-direction: column;
          margin-bottom: 30px;

          @media screen and (max-width: $breakpoint-md){
            align-items: center;
          }
    
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

          .skill-text {
            font-weight: 600;
            
            @media screen and (max-width: $breakpoint-md){
              text-align: center;
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

    @media screen and (max-width: $breakpoint-md){
      padding: 50px 0;
      width: 80%;
    }  

    .title {
      font-weight: 600;
      text-align: center
    }

    .experiences {
      display: flex;
      flex-direction: column;
      margin-top: 20px;

      @media screen and (max-width: $breakpoint-md){
        margin-top: 0;
      }  

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
          flex-direction: column;
          margin-top: 16px;

          @media screen and (max-width: $breakpoint-md) {
            flex-direction: column;
            text-align: center;
          }

          .info-text {
            display: flex;
            flex-direction: column;

            .info-upper-data {
              display: flex;
              align-items: center;
              justify-content: space-between;

              @media screen and (max-width: $breakpoint-md) {
                flex-direction: column;
                align-items: center;
              }


              .info-text-function {
                font-size: 26px;
                font-weight: 700;
                
                @media screen and (max-width: $breakpoint-md) {
                  margin-top: 10px;  
                }
              }
            }


            .info-down-data {
              display: flex;
              align-items: center;
              justify-content: space-between;
              width: 100%;

              @media screen and (max-width: $breakpoint-md) {
                flex-direction: column;
                align-items: center;
              }

              .info-text-location {
                margin-top: 20px;

                @media screen and (max-width: $breakpoint-md) {
                  margin-top: 10px;  
                }
              }

              .info-text-company {
                margin-top: 20px;
                
                @media screen and (max-width: $breakpoint-md) {
                  margin-top: 10px;  
                }
              }
            }

          }
        }
      }
    }
  }
}
</style>