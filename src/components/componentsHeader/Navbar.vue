<template>
    <section class="navbar">
          <ul class="navbar-box">
              <li class="icon-el-box" :class="{ 'active': activeName === 'Home' }" @click="setActive('Home')" title="Go to Home">
                  <div class="icon">
                    <lord-icon
                      src="https://cdn.lordicon.com/cnpvyndp.json"
                      trigger="hover"
                      colors="primary:#ffffff"
                      style="width:30px;height:30px">
                    </lord-icon>
                  </div>
                    <span>
                        HOME
                    </span>
             </li>
             <li class="icon-el-box" :class="{ 'active': activeName === 'Catalog' }" @click="setActive('Catalog')" title="Go to Catalog">
                  <div class="icon">
                    <lord-icon
                       src="https://cdn.lordicon.com/zyzoecaw.json"
                        trigger="hover"
                        colors="primary:#ffffff"
                        style="width:30px;height:30px">
                    </lord-icon>
                  </div>
                    <span>
                        CATALOG
                    </span>
             </li>
             <li class="icon-el-box" :class="{ 'active': activeName === 'about' }" @click="setActive('about')" title="Go to About">
                  <div class="icon">
                    <lord-icon
                      src="https://cdn.lordicon.com/ijahpotn.json"
                      trigger="hover"
                      colors="primary:#ffffff"
                      style="width:30px;height:30px">
                    </lord-icon>
                  </div>
                    <span>
                        ABOUT
                    </span>
             </li>
          </ul>
    </section>
</template>

<style scoped>

   .navbar {
    position: relative;
    margin-bottom: 15px;
    transition: all 0.3s, box-shadow 0.4s ease;
    background-color: #495794;
    padding: 2.5px 0;
    box-shadow: none;
    z-index: 2;
  }

   ul {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    transition: all .3s ease;
    padding: 10px 0;
    height: 40px;
    background: rgb(60,83,164);
    background: linear-gradient(95deg, rgb(46, 48, 185) 22%, rgba(0,2,6,1) 100%);
    cursor: pointer;
    z-index: 5;
  }

   ul::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 0;
    height: 100%;
    background: linear-gradient(303deg, rgb(0, 20, 108) 50%, rgb(19, 76, 189) 50%);
    box-shadow: inset 0 0 15px #000;
    z-index: -1;
    transition: width .3s ease;
  }

   .navbar:hover{
    box-shadow: 0 0 40px 5px rgba(0, 106, 193, 0.415);
    background-color: rgb(210, 222, 255);
    padding: 2.5px 0;
    animation: blink 9s linear infinite;
  }

   .navbar::before, .navbar::after {
    content: '';
    position: absolute;
    transition: width 0.2s ease-in, background-color 0.3s ease-out;
    transition-delay: 0.5s;
    width: 0;
    height: 50%;
  }

   .navbar::before {
    top: 0;
    left: 0;
  }

   .navbar::after {
    bottom: 0;
    right: 0;
  }

   .navbar:hover::before, .navbar:hover::after {
    background-color: rgb(0, 123, 255);
    width: 100%;
  }

   ul:hover{
    height: 60px;
    padding: 10px 0;
  }

   ul:hover::before {
    width: 100%;
    left: 0;
  }

   ul:hover .icon {
    margin-bottom: 10px;
  }

   ul:hover li span {
    opacity: 1;
    line-height: 2.5px;
  }

   ul li span {
    position: absolute;
    bottom: 0;
    color: #fff;
    font-size: 15px;
    font-weight: 400;
    opacity: 0;
    transition: opacity 0.2s ease;
    transition-delay: 0.2s;
    font-family: 'Roboto', sans-serif;
  }

   li {
    transition: all 0.2s ease;
    margin: 0 40px;
    text-align: center;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    filter: drop-shadow(3px 0 5px #000);
  }

   .icon {
    transition: all 0.3s;
  }

   ul li:hover {
    transform: scale(1.25);
    cursor: pointer;
    filter: drop-shadow(0 0 6px #fff) blur(0);
  }

   ul li.active {
    filter: invert(52%) sepia(96%) saturate(1739%) hue-rotate(168deg) brightness(175%) contrast(97%) drop-shadow(0 0 10px rgb(0, 179, 255));
    animation: animate 5s linear infinite;
  }

@keyframes blink {
  0% {
    box-shadow: 0 0 40px 5px rgba(0, 106, 193, 0.428);
  }
  25% {
    box-shadow: 0 0 40px 5px rgba(0, 51, 193, 0.847);
  }
  50% {
    box-shadow: 0 0 40 5px rgba(140, 0, 255, 0.65);
  }
  75% {
    box-shadow: 0 0 40px 5px rgba(0, 51, 193, 0.847);
  }
  100% {
    box-shadow: 0 0 40px 5px rgba(0, 106, 193, 0.429);
  }
}

@keyframes animate {
  0% {
    filter: 
      invert(48%) 
      sepia(96%) 
      saturate(1739%) 
      hue-rotate(168deg) 
      brightness(175%) 
      contrast(97%) 
      drop-shadow(0 0 10px rgb(0, 179, 255));
  }
  50% {
    filter: 
      invert(52%) 
      sepia(96%) 
      saturate(1739%) 
      hue-rotate(110deg) 
      brightness(175%) 
      contrast(100%) 
      drop-shadow(0 0 10px rgb(0, 255, 8));
  }
  100% {
    filter: 
      invert(48%) 
      sepia(96%) 
      saturate(1739%) 
      hue-rotate(168deg) 
      brightness(175%) 
      contrast(97%) 
      drop-shadow(0 0 10px rgb(0, 179, 255));
  }
}

</style>

<script>

export default {
    name: 'Navbar',
    data() {
      return {
        activeName: 'Home'
      }
    },
    methods: {
      setActive(name) {
          this.activeName = name;
            this.$emit('page-changed', name)
      }
    }
}
</script>