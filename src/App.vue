<template>
  <div class="all-content">
    <div class="container">
      <Header @page-changed="currentPage = $event" />
        <ChangeContent :currentPage="currentPage" />
      <Footer />
    </div>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');

  * {
    padding: 0;
    margin: 0;
  }

  .container {
    border-right: 1px solid #c0cbff62;
    border-left: 1px solid #c0cbff5c;
    overflow-x: hidden;
  }

  body {
    padding: 0 10px;
    font-family: sans-serif;
    user-select: none;
    background: #000;
    box-shadow: inset 0 0 25px #000000;
    max-width: 1900px;
  }

</style>

<script>
import Header from './components/componentsHeader/Header.vue';
import Footer from './components/Footer.vue';
import ChangeContent from './components/ChangeContent.vue'

export default {
  components: {
    Header,
    Footer,
    ChangeContent
  },
  data() {
    return {
      currentPage: 'Home',
    }
  }
}

</script>