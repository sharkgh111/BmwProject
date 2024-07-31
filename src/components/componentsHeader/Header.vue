<template>

    <header>
        <section class="upper">
          <div class="upper-content">
            <div class="bmw-logo-container">
              <div class="logo-box" v-for="(image, index) in images" :key="index">
                <a :href="image.link" target="_blank">
                  <img :src="image.url" :alt="image.alt" class="logo">
                </a>
              </div>
            </div>
          </div>
        </section>
          <Navbar @page-changed="handlePageChanged" />
    </header>

</template>

<style scoped>

  header {
    padding: 10px 0 5px 0;
    max-width: 100%;
    background: linear-gradient(90deg, #060c20, #0c135e, #08112d);
    box-shadow: inset 0 0 20px #000;
    position: relative;
    z-index: 1000;
  }

  header .upper {
    padding: 0 20px;
    margin-bottom: 20px;
  }

  header .upper-content {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  header .bmw-logo-container {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    width: 100%;
  }

  header .logo-box:nth-last-child(-n+2) {
    width: 165px;
  }

  header .logo-box {
    display: block;
    width: 100px;
    margin-bottom: 10px;
    transition: all 0.2s ease;
    filter: drop-shadow(10px 0 15px #000);
  }
  
  header .logo-box img {
    width: 100%;
  }

  header .logo-box:hover {
    transform: scale(1.2);
    cursor: pointer;
    filter: drop-shadow(0 0 20px #6080ff72) brightness(110%);
  }

  header .main-logo {
    width: 85px;
  }

  header .main-logo img {
    width: 100%;
  }

  header .text-logo {
    width: 160px;
  }

  header .text-logo img {
    width: 100%;
  }

  @media (max-width: 500px) {

    header .bmw-logo-container {
      flex-wrap: wrap;
      gap: 20px;
    }

    header .bmw-logo-container .logo-box:nth-last-child(-n+2) {
      width: 120px;
    }

  }
  
</style>

<script>
import Navbar from '../componentsHeader/Navbar.vue'

export default {
    name: 'Header',
    components: {
      Navbar
    },
    data() {
      return {
        images: [
          { url: '/logo/bmwilogo.png', alt: 'Bmw image 1', link: 'https://www.bmw.ua/uk/all-models/bmw-i.html' },
          { url: '/logo/bmwmlogo.png', alt: 'Bmw image 2', link: 'https://www.bmw.ua/uk/all-models/m-series.html' },
          { url: '/logo/bmwxlogo.png', alt: 'Bmw image 3', link: 'https://www.bmw.ua/uk/all-models/x-series.html' },
          { url: '/logo/bmwixlogo.png', alt: 'Bmw image 5', link: 'https://www.bmw.ua/uk/all-models/bmw-i/bmw-ix/2021/bmw-ix.html' },
        ],
      }
    },
    methods: {
      handlePageChanged(page) {
        this.$emit('page-changed', page);
      }
    }
  }
</script>