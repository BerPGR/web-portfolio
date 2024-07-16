<template>
  <div class="contact-section" :style="{backgroundColor: colors.amarelo}">
    <div class="container">
      <div class="contact-left-section">
        <div class="title">
          <p :style="{ color: colors.roxo }">Contact</p>
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
        <div class="say-hi">
          <p>👋🏼 Say Hi!</p>
        </div>
      </div> 
    </div>

    <div class="footer">
      <div class="divider"></div>
      <div class="footer-info">
        <p>&copy; 2024 All Right Deserved</p>
        <p>Made By Bernardo Matuchewski</p>
        <p>bernardopgr27@hotmail.com</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import colors from "../assets/colors/colors";

const contacts = [
  {type: 'Email', text: 'bernardopgr27@hotmail.com', icon: 'fa-solid fa-envelope'},
  {type: 'Number', text: '+55 (47) 99673-7614', icon: 'fa-solid fa-phone'}
]

</script>

<style scoped lang="scss">
.contact-section {
    min-height: 100vh;
    display: flex;
    flex-direction: column;

    .container {
      display: flex;

      .contact-left-section {
        width: 50%;
        padding: 40px 0 30px 100px;
        display: flex;
        flex-direction: column;
  
        .title {
          p {
            font-size: 16px;
            transform: rotate(330deg);
            display: inline-block;
            font-weight: 600;
          }
  
          h1 {
            font-size: 52px;
            font-weight: 700;
            margin-top: 16px
          }
        }
  
        .contact-container {
          display: flex;
          flex-direction: column;
          width: 80%;
          margin-top: 40px;
        
          .divider {
            width: 100%;
            height: 2px;
          }
  
          .contact-info {
            display: flex;
            margin-top: 30px;
  
            .icon {
                padding: 20px;
                background-color: white;
                border-radius: 100%
            }
  
            .info-text {
              margin-left: 40px;
              display: flex;
              flex-direction: column;
              justify-content: space-between;
  
              .type {
                font-weight: 400;
              }
  
              .text {
                font-size: 20px;
                font-weight: 600;
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
    
        .say-hi {
          display: flex;
          border-radius: 100%;
          width: 300px;
          border: 2px solid black;
          height: 300px;
          background-color: transparent;
          align-items: center;
          justify-content: center;
          
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
      }
    }

}
</style>