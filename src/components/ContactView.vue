<template>
  <div class="contact-section" :style="{backgroundColor: colors.amarelo}">
    <div class="container">
      <div class="contact-left-section">
        <div class="title">
          <p>Contact</p>
          <h1>Let's Discuss Your Project</h1>
        </div>
  
        <div class="contact-container" v-for="(contact, i) in contacts" :key="i">
          <div class="divider" :style="{ backgroundColor: colors.preto }"></div>
          <div class="contact-info">
            <div class="icon">
              <i :class="contact.icon" />
            </div>
            <div class="info-text">
              <p class="type">{{ contact.type }}</p>
              <p class="text">{{ contact.text }}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="contact-right-section">
        <a href="https://www.linkedin.com/in/bernardomm27/" target="blank" :style="{textDecoration: 'none', color: colors.preto}">
          <div class="say-hi">
            <p>Say Hi!</p>
          </div>
        </a>
      </div> 
    </div>

    <div class="footer">
      <div class="divider"></div>
      <div class="footer-info">
        <p>&copy; 2024 All Right Deserved</p>
        <p class="made-by">Made By Bernardo Matuchewski</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import colors from "../assets/colors/colors";

const contacts = [
  {type: 'Email', text: 'bernardopgr27@hotmail.com', icon: 'fa-solid fa-envelope'},
  {type: 'Number', text: '+55 (47) 99673-7614', icon: 'fa-solid fa-phone'}
]

const isLargeScreen = computed(() => {
  return window.screen.width > 992 
})

</script>

<style scoped lang="scss">
$breakpoint-xs: 576px;
$breakpoint-sm: 768px;
$breakpoint-md: 992px;
$breakpoint-lg: 1200px;
$breakpoint-xl: 1400px;

.contact-section {
    min-height: 100vh;
    display: flex;
    flex-direction: column;

    .container {
      display: flex;

      
    @media screen and (max-width: $breakpoint-md){
      flex-direction: column;
      align-items: center;
      text-align: center;
      padding: 40px 0;
    }

      .contact-left-section {
        width: 50%;
        padding: 40px 0 30px 100px;
        display: flex;
        flex-direction: column;

        @media screen and (max-width: $breakpoint-md){
          padding: 0;
          width: 80%;
        }
  
        .title {
          @media screen and (max-width: $breakpoint-md){
            text-align: center;
            flex-direction: column;
            display: flex;
            align-items: center;
          }

          p {
            font-size: 16px;
            transform: rotate(330deg);
            display: inline-block;
            font-weight: 600;
            color: #8873EF;

            @media screen and (max-width: $breakpoint-md){
              text-align: center;
              transform: rotate(0deg);
              display: flex;
              font-size: 24px;
              font-weight: bold;
            }
          }
  
          h1 {
            font-size: 52px;
            font-weight: 700;
            margin-top: 16px;

            @media screen and (max-width: $breakpoint-md){
              text-align: center;
              font-size: 36px;
              margin-top: 0;
            }
          }
        }
  
        .contact-container {
          display: flex;
          flex-direction: column;
          width: 80%;
          margin-top: 40px;

          @media screen and (max-width: $breakpoint-md){
            width: 100%;
          }
        
          .divider {
            width: 100%;
            height: 2px;
          }
  
          .contact-info {
            display: flex;
            margin-top: 30px;

            @media screen and (max-width: $breakpoint-md){
              flex-direction: column;
              align-items: center;
              text-align: center;
            }
  
            .icon {
                display: flex;
                align-items: center;
                justify-content: center;
                padding: 20px;
                background-color: white;
                border-radius: 100%;

                @media screen and (max-width: $breakpoint-md){
                  padding: 20px;
                  width: 40px;
                  height: 40px;
                }
            }
  
            .info-text {
              margin-left: 40px;
              display: flex;
              flex-direction: column;
              justify-content: space-between;

              @media screen and (max-width: $breakpoint-md){
                margin-left: 0;
              }

  
              .type {
                font-weight: 400;

                @media screen and (max-width: $breakpoint-md){
                  margin-top: 10px;
                }
              }
  
              .text {
                font-size: 20px;
                font-weight: 600;

                
                @media screen and (max-width: $breakpoint-md){
                  margin-top: 10px;
                }
              }
            }
        }
      }
      }

      .contact-right-section {
        display: flex;
        width: 50%;
        justify-content: center;
        align-items: center;

        @media screen and (max-width: $breakpoint-md) {
          margin-top: 60px;
        }
    
        .say-hi {
          display: flex;
          border-radius: 100%;
          width: 300px;
          border: 2px solid black;
          height: 300px;
          background-color: transparent;
          align-items: center;
          justify-content: center;
          cursor: pointer;

          @media screen and (max-width: $breakpoint-xs) {
            height: 150px;
            width: 150px;
          }
          
          p {
            font-size: 28px;
            font-weight: 600;
          }
        }
      }
    }
    
    .footer {
      margin-top: 120px;
      width: 100%;
      padding: 0 100px;
      text-align: center;

      @media screen and (max-width: $breakpoint-md) {
        padding: 0 100px 40px 100px;
        margin-top: 40px;
      }

      .divider {
        width: 100%;
        height: 2px;
        background-color: black;
      }

      .footer-info {
        margin-top: 10px;
        display: flex;
        align-items: center;
        justify-content: space-between;

        @media screen and (max-width: $breakpoint-xs) {
          justify-content: center;
        }

        .made-by {
          @media screen and (max-width: $breakpoint-xs) {
            display: none
          }
        }
      }
    }

}
</style>