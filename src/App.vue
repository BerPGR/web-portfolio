<script setup>
import HomeView from './components/HomeView.vue';
import ServiceView from './components/ServicesView.vue';
import PortfolioView from './components/PortfolioView.vue';
import ContactView from './components/ContactView.vue';
import colors from './assets/colors/colors.js' 


const headerSelectors = ['About', 'Service', 'Portfolio', 'Contact']

const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId)
  if (section) {
    section.scrollIntoView({behavior: 'smooth'})
  }
}
</script>

<template>
  <div>
    <header>
      <nav>
          <ul>
              <li v-for="(selector, i) in headerSelectors" :key="i" @click="scrollToSection(selector)">{{selector}}</li>
          </ul>
      </nav>
    </header>
    <HomeView id="About"/>
    <ServiceView id="Service"/>
    <PortfolioView id="Portfolio"/>
    <ContactView id="Contact"/>
  </div>
</template>

<style scoped style="scss">
header{
  z-index: 2;
  background-color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80px;
  width: 100%;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);;

  nav {
      ul {
          list-style: none;
          display: flex;

          li {
              display: inline-block;
              position: relative;
              margin: 0 14px;
              cursor: pointer;
              font-weight: 500;
            
              &::after {
                content: '';
                position: absolute;
                width: 100%;
                height: 1.5px;
                bottom: 0;
                left: 0;
                background-color: black;
                transform: scaleX(0);
                transform-origin: right;
                transition: transform 0.3s ease-out;
              }
            
              &:hover::after {
                transform: scaleX(1);
                transform-origin: left;
              }
            }
      }
  }
}
footer {
  color: white;
  padding: 10px;
  height: 40px;
  background-color: #898989;
  display: flex;
  align-items: center;
  justify-content: space-around;

  img {
    height: 20px;
  }
}
</style>
