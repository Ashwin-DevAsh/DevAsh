<template>
  <div class="homepage">
    <Header />
    <div style="margin-top:-1px;">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#884bdf"
          fill-opacity="1"
          d="M0,160L80,144C160,128,320,96,480,122.7C640,149,800,235,960,234.7C1120,235,1280,149,1360,106.7L1440,64L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
        />
      </svg>
    </div>

    <Services />
    <Portfolio />
    <About />
    <Contact />
  </div>
</template>

<script>
import Header from "../components/Header";
import Portfolio from "../components/portfolio";
import Services from "../components/Services";
import About from "../components/About";
import Contact from "../components/contact";
export default {
  name: "Homepage",
  components: {
    Header,
    Services,
    Portfolio,
    About,
    Contact
  }
};
</script>

<style scoped>
.homepage {
  display: flex;
  flex-direction: column;
  justify-content: start;
}
</style>
