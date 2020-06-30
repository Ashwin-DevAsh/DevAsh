<template>
  <div>
    <Header></Header>
    <div>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#884bdf"
          fill-opacity="1"
          d="M0,160L80,144C160,128,320,96,480,122.7C640,149,800,235,960,234.7C1120,235,1280,149,1360,106.7L1440,64L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
        />
      </svg>
    </div>
    <Services></Services>

    <div style="height:100vh"></div>
    <div style="height:100vh" class="page4"></div>
  </div>
</template>

<script>
import Header from "../components/Header";
import Services from "../components/Services";
export default {
  name: "Homepage",
  components: {
    Header,
    Services
  }
};
</script>

<style scoped></style>
