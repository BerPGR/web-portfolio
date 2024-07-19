<template>
  <div id="section-service" class="section-service" :style="{ backgroundColor: colors.amarelo }">
    <div class="service-left-section">
      <div class="service-title">
        <p :style="{ color: colors.roxo }" class="little-text">Service</p>
        <h1>Services I <br>Offer</h1>
        <p class="my-service-text">I help ambitous business like your generate more profits by building excelent websites, breathtaking apps and services to connect you to more clients</p>
      </div>
    </div>
    <div class="service-right-section">
      <div class="services">
        <div class="services-container" v-for="(service, i) in services" :key="i">
          <div class="divider"></div>
          <div class="info-container">
            <h3 :style="{ fontSize: '16px', fontWeight: '600'}" class="info-number">0{{ (i+1) }}/</h3>
            <div class="info-text">
              <h1 class="info-text-title">{{service.title}}</h1>
              <div class="explore">
                <p>Explore</p>
                <a :href="service.link" target="blank">
                <div class="explore-button" :style="{ backgroundColor: colors.roxo}">
                  <i :style="{ color: colors.branco }" class="fa-solid fa-arrow-trend-up" />
                </div></a>
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
  {title: 'Mobile App Development', link: 'https://github.com/BerPGR?tab=repositories&q=&type=&language=dart&sort='},
  {title: 'Website Development', link: 'https://github.com/BerPGR?tab=repositories&q=&type=&language=vue&sort='},
  {title: 'Back-End Development', link: 'https://github.com/BerPGR?tab=repositories&q=&type=&language=java&sort='}
]
</script>

<style scoped lang="scss">
$breakpoint-xs: 576px;
$breakpoint-sm: 768px;
$breakpoint-md: 992px;
$breakpoint-lg: 1200px;
$breakpoint-xl: 1400px;

.section-service {
  min-height: 100vh;
  display: flex;

  @media screen and (max-width: $breakpoint-md){
    flex-direction: column;
    align-items: center;
    padding: 40px 0;
  }

  .service-left-section {
    width: 50%;
    padding: 40px 0 30px 100px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    @media screen and (max-width: $breakpoint-md){
      width: 80%;
      padding: 0;
    }
    
    .service-title {
      @media screen and (max-width: $breakpoint-md){
       display: flex;
       flex-direction: column;
       align-items: center;
      }

      .little-text {
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

      h1 {
        font-size: 52px;
        font-weight: 700;
        margin-top: 16px;

        @media screen and (max-width: $breakpoint-md){
          text-align: center;
          margin-top: 0;
          font-size: 36px;
        }
      }

      .my-service-text {
        width: 80%; 
        line-height: 32px; 
        margin-top: 16px;

        @media screen and (max-width: $breakpoint-md) {
          text-align: center;
          width: 100%; 
        }
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

    @media screen and (max-width: $breakpoint-md){
      padding: 0;
      width: 80%;
    }

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

          @media screen and (max-width: $breakpoint-md) {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center
          }

          .info-number {
            @media screen and (max-width: $breakpoint-md) {
              display: none
            }
          }

          .info-text {
            display: flex;
            flex-direction: column;
            margin-left: 32px;
            width: 100%;

            @media screen and (max-width: $breakpoint-md) {
              margin-left: 0;
            }

            .info-text-title {
              font-size: 46px;
              font-weight: 600;

              @media screen and (max-width: $breakpoint-md){
                font-size: 32px;
                text-align: center;
              }
            }

            .explore {
              margin-top: 30px;
              display: flex;
              align-items: center;
              justify-content: space-between;

              @media screen and (max-width: $breakpoint-md) {
                flex-direction: column;
                margin-top: 10px;  
              }

              .explore-button {
                padding: 15px;
                border-radius: 100%;
                cursor: pointer;

                @media screen and (max-width: $breakpoint-md){
                  padding: 10px;
                  margin-top: 8px;
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