<template>
  <div id="section-service" class="section-service" :style="{ backgroundColor: colors.amarelo }">
    <div class="service-left-section">
      <div class="service-title">
        <p :style="{ color: colors.roxo }" class="little-text">Service</p>
        <h1>Services I <br>Offer</h1>
        <p :style="{ width: '80%', lineHeight:'32px', marginTop: '16px'}">I help ambitous business like your generate more profits by building excelent websites, breathtaking apps and services to connect you to more clients</p>
      </div>

      <button>View all services I offer</button>
    </div>
    <div class="service-right-section">
      <div class="services">
        <div class="services-container" v-for="(service, i) in services" :key="i">
          <div class="divider"></div>
          <div class="info-container">
            <h3 :style="{ fontSize: '16px', fontWeight: '600'}">0{{ (i+1) }}/</h3>
            <div class="info-text">
              <h1 :style="{fontSize: '46px', fontWeight: '600'}">{{service.title}}</h1>
              <div class="explore">
                <p>Explore</p>
                <div class="explore-button" :style="{ backgroundColor: colors.roxo}">
                  <i :style="{ color: colors.branco }" class="fa-solid fa-arrow-trend-up" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import colors from "../assets/colors/colors";

const services = [
  {title: 'Mobile App Development'},
  {title: 'Website Development'},
  {title: 'Back-End Development'}
]
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
    justify-content: space-between;
    
    .service-title {

      .little-text {
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
    
    button {
      width: 80%;
      padding: 10px;
      font-size: 20px;
      font-weight: 600;
      color: white;
      background-color: #8873EF;
      cursor: pointer;
      border: none;
      border-radius: 5px;
      transition: 150ms ease-in-out;

      &:hover {
        background-color: white;
        color: black;
      }
    }
  }
  
  .service-right-section {
    display: flex;
    flex-direction: column;
    width: 50%;
    padding: 40px 100px 0 0;

    .services {
      display: flex;
      flex-direction: column;
      margin-top: 20px;

      .services-container {
        display: flex;
        flex-direction: column;
        margin-top: 20px;

        &:first-child {
          margin-top: 0px;
        }

        .divider {
          margin-bottom: 6px;
          background-color: black;
          height: 2px;
          width: 100%;
        }

        .info-container {
          display: flex;
          margin-top: 16px;

          .info-text {
            display: flex;
            flex-direction: column;
            margin-left: 32px;
            width: 100%;

            .explore {
              margin-top: 30px;
              display: flex;
              align-items: center;
              justify-content: space-between;

              .explore-button {
                padding: 15px;
                border-radius: 100%;
                cursor: pointer;
              }
            }
          }
        }
      }
    }
  }
}
</style>