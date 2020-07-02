<template>
  <div class="header-container">
    <vue-particles
      class="particles"
      color="#dedede"
      :particleOpacity="0.7"
      :particlesNumber="80"
      shapeType="circle"
      :particleSize="4"
      linesColor="#dedede"
      :linesWidth="2"
      :lineLinked="true"
      :lineOpacity="0.4"
      :linesDistance="150"
      :moveSpeed="3"
      :hoverEffect="true"
      hoverMode="grab"
      :clickEffect="true"
      clickMode="push"
    ></vue-particles>

    <div style="height:100%;display:flex;flex-direction:column-reverse">
      <div style="height:20px;" class="page2"></div>
    </div>

    <nav class="navBar" v-bind:class="{ scrolled: isScrolled }">
      <div id="logo-container">
        <div class="logo" :class="{ 'shake-animation': shakeThis }">
          <img :src="logo" alt />
          <div class="logo-title">
            <h4>{{ title }}</h4>
          </div>
        </div>

        <div v-on:click="menuOpen()" class="hamburger">
          <div id="line1" class="line"></div>
          <div id="line2" class="line"></div>
          <div id="line3" class="line"></div>
        </div>
      </div>

      <div class="menu-container" :class="{ menuOpen: isMenuOpen }">
        <div v-on:click="scroll('.header-container')" :class="{ selected: currentPage == 1 }">
          <h5>Home</h5>
        </div>
        <div v-on:click="scroll('.page2')" :class="{ selected: currentPage == 2 }">
          <h5>Services</h5>
        </div>
        <div v-on:click="scroll('.page3')" :class="{ selected: currentPage == 3 }">
          <h5>Portfolio</h5>
        </div>
        <div :class="{ selected: currentPage == 4 }" v-on:click="scroll('.page4')">
          <h5>Contact</h5>
        </div>
      </div>
    </nav>

    <div class="main-container">
      <div class="title-container">
        <h1>{{ mainTitle }}</h1>
        <div class="underline"></div>
      </div>
      <div class="image-container">
        <img src="../assets/dev.svg" alt />
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import VueParticles from "vue-particles";
Vue.use(VueParticles);

export default {
  mounted() {
    this.onScroll();
    window.addEventListener("scroll", this.onScroll);
    this.shake();
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.onScroll);
  },
  data() {
    return {
      logo: require("../assets/logo.svg"),
      title: "DevAsh",
      subTitle: "Development & Solutions",
      mainTitle: "freelancing service",
      software: "{  }",
      website: "< Website />",
      isScrolled: false,
      currentPage: 1,
      isMenuOpen: false,
      shakeThis: false
    };
  },
  methods: {
    scroll(page) {
      if (this.isMenuOpen) {
        this.isMenuOpen = false;
        setTimeout(() => {
          document.querySelector(page).scrollIntoView();
        }, 1000);
      } else {
        document.querySelector(page).scrollIntoView();
      }
    },

    getWidth() {
      return window.innerWidth;
    },

    menuOpen() {
      (this.isMenuOpen = !this.isMenuOpen), console.log(this.isMenuOpen);
    },

    onScroll() {
      var scrollTop =
        window.pageYOffset !== undefined
          ? window.pageYOffset
          : (
              document.documentElement ||
              document.body.parentNode ||
              document.body
            ).scrollTop;
      var section = document.body.scrollHeight / 4;
      if (scrollTop > section * 2.7) {
        this.currentPage = 4;
      } else if (scrollTop > section * 1.7) {
        this.currentPage = 3;
      } else if (scrollTop > section * 0.7) {
        this.currentPage = 2;
      } else {
        this.currentPage = 1;
      }

      if (scrollTop < 10) {
        this.isScrolled = false;
      } else {
        this.isScrolled = true;
      }
    },

    shake() {
      let that = this;
      setInterval(function() {
        that.shakeThis = true;
        setTimeout(() => {
          that.shakeThis = undefined;
        }, 1000);
      }, 5000);
    }
  }
};
</script>

<style scoped>
.header-container {
  overflow-x: hidden;
  height: 95vh;
  margin: 0%;

  width: 100%;
  background: linear-gradient(#5e56e9, #884bdf);
}
.particles {
  height: 90vh;
  position: absolute;
  z-index: 0;
  width: 100%;
}
#image-cover {
  position: absolute;
  top: 0%;
  height: 100vh;
  width: 100%;
  background-color: black;
  z-index: 2;
  opacity: 0.7;
}

.underline {
  height: 2px;
  width: 60px;
  margin-top: 40px;
  margin-left: 5px;
  background-color: #fb397d;
  animation-delay: 2s;
  opacity: 0;
  transform: scale(0.7);
  animation: animation-title;
  animation-delay: 2s;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
}

.navBar {
  height: 70px;
  width: 100%;
  position: fixed;
  top: 0%;
  transition: 0.3s ease;
  display: grid;
  align-items: center;
  justify-content: center;
  grid-template-columns: 60% 40%;
  z-index: 3;
}

.line {
  width: 30px;
  height: 2px;
  background: white;
  margin: 3.5px;
}

#line1 {
  width: 30px;
}
#line2 {
  width: 20px;
}
#line3 {
  width: 10px;
}

.hamburger {
  display: none;
  right: 10px;
  position: absolute;
  cursor: pointer;
}

.logo-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.logo {
  height: 45px;
  width: 190px;
  display: flex;
  align-items: center;
  border-top-right-radius: 30px;
  border-bottom-left-radius: 30px;
  font-size: 1.4rem;
  background-color: #fb397d;
  margin-left: 60px;
  box-shadow: inset 5px 5px 10px #f33779, inset -5px -5px 10px #ff3b81;
}

.logo img {
  height: 30px;
  width: 30px;
  margin-left: 15px;
}

.logo-title {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-left: 15px;
}

.logo h4,
h6 {
  color: white;
  margin: 0%;
}

.logo h6 {
  font-size: 8px;
  opacity: 0.8;
}

.menu-container {
  display: flex;
  flex-direction: row;
  color: white;
}

.menu-container h5 {
  display: flex;
  opacity: 0.9;
  padding: 5px 0px;
  flex-direction: row;
  color: white;
  margin: 0% 30px;
}

.menu-container .selected {
  border-bottom: solid 1.5px #fb397d;
}

.menu-container :hover {
  cursor: pointer;
  opacity: 1;
}

.image-container img {
  max-width: 400px;
  position: relative;
  opacity: 0px;
  transform: scale(0.7);
  animation-fill-mode: forwards;
  animation-name: image-animation;
  animation-delay: 0.3s;
  opacity: 0;
  animation-duration: 1s;
  object-fit: scale-down;
  z-index: 2;
}

@keyframes image-animation {
  from {
    opacity: 0;
    transform: translateX(100%) scale(0.7);
  }
  to {
    opacity: 1;
    transform: translateX(0%) scale(1);
  }
  /* from {
    opacity: 0;
    transform: translateY(50%) scale(0.7);
  }
  to {
    opacity: 1;
    transform: translateY(0%) scale(1);
  } */
}

.main-container {
  height: 100vh;
  width: 100%;
  position: absolute;
  top: 0%;
  justify-content: space-between;
  align-self: flex-end;
  justify-self: flex-end;
  display: grid;
  grid-template-columns: 50% 50%;
  grid-template-rows: 1fr 1fr 1fr;
  align-items: center;
  overflow-x: hidden;
}

.title-container {
  margin-left: 60px;
  max-width: 500px;
  grid-row: 2/3;
}

.image-container {
  grid-row: 3/4;
  grid-column: 2/3;
  animation-fill-mode: forwards;
  align-self: center;
  justify-self: center;
}

.title-container h1 {
  font-size: 4rem;
  margin: 0%;
  color: white;
  animation-name: animation-title;
  animation-delay: 1s;
  transform: scale(0.7);
  animation-duration: 1s;
  opacity: 0;
  animation-fill-mode: forwards;
}

@keyframes animation-title {
  from {
    opacity: 0;
    transform: translateX(-100%) scale(0.7);
  }
  to {
    opacity: 1;
    transform: translateX(0%) scale(1);
  }
}

.title-container p {
  opacity: 0;
  color: white;
}

.scrolled {
  background: #884bdf;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.04), 0 6px 6px rgba(0, 0, 0, 0.04);
}

mark {
  background: transparent;
  color: #fb397d;
}

@media (max-width: 1140px) {
  .navBar {
    grid-template-columns: 50% 50%;
  }
}

@media (max-width: 850px) {
  .title-container {
    grid-column: 1/4;
    margin-bottom: 80px;
  }

  .image-container img {
    max-width: 300px;
  }

  .menu-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    position: absolute;
    top: 0%;
    z-index: -1;
    padding-bottom: 15px;
    background: #884bdf;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.05), 0 6px 6px rgba(0, 0, 0, 0);
    padding-top: 70px;
    transition: all 0.5s ease-out;
    clip-path: circle(100px at 100% -50%);
    font-size: 1.3rem;
  }

  .logo {
    margin-left: 20px;
  }

  .title-container {
    margin-left: 20px;
  }

  .menuOpen {
    clip-path: circle(1000px at 90% 10%);
  }

  .menu-container div {
    padding: 10px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .menu-container .selected {
    border-bottom: none;
    color: #fb397d;
  }

  .menu-container .selected h5 {
    opacity: 1;
    font-weight: bolder;
    color: #fb397d;
  }

  #logo-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .navBar {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: flex-start;
  }

  .hamburger {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    justify-content: center;
  }
}

@media (max-width: 600px) {
  .title-container {
    margin-bottom: 120px;
  }

  .title-container h1 {
    font-size: 3.3rem;
  }
  .image-container {
    grid-column: 1/3;

    justify-self: center;
  }

  .image-container img {
    width: 270px;
  }
}

@media (max-width: 450px) {
  .image-container {
    display: none;
  }

  .title-container h1 {
    font-size: 3rem;
  }
}

.shake-animation {
  /* Start the shake animation and make the animation last for 0.5 seconds */
  animation: shake 0.5s;
  /* When the animation is finished, start again */
  animation-iteration-count: infinite;
}

@keyframes shake {
  10%,
  90% {
    transform: translate3d(-1px, 0, 0);
  }

  20%,
  80% {
    transform: translate3d(2px, 0, 0);
  }

  30%,
  50%,
  70% {
    transform: translate3d(-4px, 0, 0);
  }

  40%,
  60% {
    transform: translate3d(4px, 0, 0);
  }
}
</style>
