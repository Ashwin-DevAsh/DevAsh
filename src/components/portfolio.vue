<template>
  <div class="portfolio">
    <div class="title-container">
      <div class="title">
        <h1>Our Portfolios</h1>
        <div class="underline"></div>
      </div>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#884bdf"
          fill-opacity="1"
          d="M0,128L30,106.7C60,85,120,43,180,48C240,53,300,107,360,138.7C420,171,480,181,540,165.3C600,149,660,107,720,90.7C780,75,840,85,900,112C960,139,1020,181,1080,186.7C1140,192,1200,160,1260,133.3C1320,107,1380,85,1410,74.7L1440,64L1440,320L1410,320C1380,320,1320,320,1260,320C1200,320,1140,320,1080,320C1020,320,960,320,900,320C840,320,780,320,720,320C660,320,600,320,540,320C480,320,420,320,360,320C300,320,240,320,180,320C120,320,60,320,30,320L0,320Z"
        />
      </svg>
    </div>

    <div class="main-container">
      <div class="image-container"></div>
    </div>

    <div class="footer">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#5e56e9"
          fill-opacity="1"
          d="M0,224L30,234.7C60,245,120,267,180,256C240,245,300,203,360,202.7C420,203,480,245,540,245.3C600,245,660,203,720,160C780,117,840,75,900,69.3C960,64,1020,96,1080,144C1140,192,1200,256,1260,272C1320,288,1380,256,1410,240L1440,224L1440,0L1410,0C1380,0,1320,0,1260,0C1200,0,1140,0,1080,0C1020,0,960,0,900,0C840,0,780,0,720,0C660,0,600,0,540,0C480,0,420,0,360,0C300,0,240,0,180,0C120,0,60,0,30,0L0,0Z"
        />
      </svg>
    </div>
  </div>
</template>

<script>
import { Carousel3d, Slide } from "vue-carousel-3d";

export default {
  components: {
    Carousel3d,
    Slide,
  },

  mounted() {
    document.querySelector(".owl-stage-outer").classList.add("dots");
  },

  data() {
    return {
      images: [
        "https://i.ya-webdesign.com/images/android-phone-png-6.png",
        "https://i.ya-webdesign.com/images/android-phone-png-6.png",
        "https://i.ya-webdesign.com/images/android-phone-png-6.png",
        "https://i.ya-webdesign.com/images/android-phone-png-6.png",
        "https://i.ya-webdesign.com/images/android-phone-png-6.png",
      ],
    };
  },
};
</script>

<style scoped>
.portfolio {
  display: flex;
  flex-direction: column;
}
.main-container {
  height: 100vh;
  margin-top: -20px;
  background: linear-gradient(#884bdf, #5e56e9);
}

.image-container {
  margin-top: 50px;
  width: 100%;
  height: 80%;
  display: flex;
  color: #fb397d;
}

.images {
  margin-bottom: 100px;
}

.dots {
  display: none;
}

.title {
  margin-top: 150px;
  position: absolute;
  width: 100%;
  flex-direction: column;
  display: flex;
  color: white;
  align-items: center;
  justify-content: center;
}
.underline {
  height: 2px;
  width: 60px;
  background-color: #fb397d;
}
</style>
