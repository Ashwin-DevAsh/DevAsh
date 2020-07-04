<template>
  <div class="portfolio">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
      <path
        fill="#884bdf"
        fill-opacity="1"
        d="M0,128L30,106.7C60,85,120,43,180,48C240,53,300,107,360,138.7C420,171,480,181,540,165.3C600,149,660,107,720,90.7C780,75,840,85,900,112C960,139,1020,181,1080,186.7C1140,192,1200,160,1260,133.3C1320,107,1380,85,1410,74.7L1440,64L1440,320L1410,320C1380,320,1320,320,1260,320C1200,320,1140,320,1080,320C1020,320,960,320,900,320C840,320,780,320,720,320C660,320,600,320,540,320C480,320,420,320,360,320C300,320,240,320,180,320C120,320,60,320,30,320L0,320Z"
      />
    </svg>

    <div class="main-container">
      <div class="title">
        <h1>Our Portfolios</h1>
        <div class="underline"></div>
      </div>

      <div class="image-container">
        <Carousel
          class="carousel"
          :per-page="1"
          :autoplay="true"
          :loop="true"
          :autoplayTimeout="5000"
          :mouse-drag="true"
          :navigationEnabled="true"
          :paginationEnabled="true"
          :navigationClickTargetSize="5"
          paginationActiveColor="#fb397d"
        >
          <Slide class="slide" v-for="(i, index) in portfolios" :key="index">
            <div class="images">
              <img class="app-image" :src="i.image" />
              <div class="title-container">
                <h1>{{ i.title }}</h1>
                <p>{{ i.subTitle }}</p>
                <div class="links">
                  <a :href="i.link" target="_blank">
                    <div class="github">
                      <img src="../assets/github.svg" alt />
                      <h5>Github</h5>
                    </div>
                  </a>
                </div>
              </div>
            </div>
          </Slide>
        </Carousel>
      </div>
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
    <div class="page4" style="height:90px"></div>
  </div>
</template>

<script>
import vue from "vue";
import { Carousel, Slide } from "vue-carousel";
export default {
  components: { Carousel, Slide },

  methods: {
    next() {
      if (this.current < this.images.length) this.current += 1;
    },
    prev() {
      if (this.current > 0) this.current -= 1;
    }
  },

  mounted() {
    vue.nextTick(() => {});
  },

  data() {
    return {
      current: 0,
      portfolios: [
        {
          image: require("../assets/portfolioImages/farmtohome.png"),
          title: "Farm To Home",
          subTitle:
            "Aa app to connect farmers and a consumers directly with out a middle men and helps farmers to sell their agricultural goods",
          link: "https://github.com/Ashwin-DevAsh"
        },
        {
          image: require("../assets/portfolioImages/recwallet.png"),
          title: "Rec Wallet",
          subTitle:
            "Blockchain based cryptocurrency app build on top of our own private ledger system.",
          link: "https://github.com/Ashwin-DevAsh/Rec-Wallet-Client.git"
        },

        {
          image: require("../assets/portfolioImages/sway.png"),
          title: "Sway",
          subTitle:
            "A fully functional kiosk solution for a enterprise which enables to access a client devices remotely",
          link: "https://github.com/Ashwin-DevAsh"
        },
        {
          image: require("../assets/portfolioImages/rm.png"),
          title: "R M Traders",
          subTitle:
            "An admin app that maintain a agricultural and financial bussiness.",
          link: "https://github.com/Git-Ashwin/R_M_Traders.git"
        },
        {
          image: require("../assets/portfolioImages/rec.png"),
          title: "Rec Mech",
          subTitle:
            "App to maintain a library stocks with qr scan and also helps to monitor student activites",
          link: "https://github.com/Git-Ashwin/recmechlib.git"
        }
      ]
    };
  }
};
</script>

<style scoped>
.portfolio {
  overflow-x: hidden;
  display: flex;
  flex-direction: column;
}
.main-container {
  height: 100vh;
  display: flex;
  flex-direction: column;
  margin-top: -20px;
  background: linear-gradient(#884bdf, #5e56e9);
}

.carousel {
  height: 80vh;
}

.slide {
  height: 70vh;
}

a {
  text-decoration: none;
  color: white;
}

.image-container {
  width: 100%;
  height: 80%;
  display: flex;
  flex-direction: column;
}

.next {
  grid-column: 4;
  height: 100%;
  grid-row: 2;
  width: 100%;
}

.next,
.prev {
  align-self: center;
  justify-self: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.next img,
.prev img {
  height: 50px;
}

.prev {
  grid-column: 1;
  height: 100%;
  width: 100%;
  grid-row: 2;
}

.title {
  margin-top: -100px;
  margin-bottom: 100px;
  width: 100%;
  flex-direction: column;
  display: flex;
  color: white;
  align-items: center;
  justify-content: center;
}
.title h1 {
  font-size: 3rem;
}

.title-container p {
  opacity: 0.7;
}
.underline {
  height: 2px;
  width: 60px;
  background-color: #fb397d;
}

.images {
  display: grid;
  width: 100%;

  color: white;
  height: 100%;
  grid-template-columns: 10% repeat(2, 1fr) 10%;
  grid-template-rows: 5fr repeat(2, 1fr);
}

.app-image {
  height: 500px;
  grid-column: 2/3;
  grid-row: 2/3;
}

.title-container {
  grid-column: 3/4;
  grid-row: 2/3;
}

.links {
  margin-top: 60px;
  display: flex;
  justify-content: start;
  align-items: center;
}

.github {
  height: 45px;
  width: 190px;
  cursor: pointer;
  padding: 5px 0px;
  display: flex;
  align-items: center;
  border-top-right-radius: 30px;
  border-bottom-left-radius: 30px;
  font-size: 1.4rem;
  background-color: #181818;
  display: flex;
  justify-content: start;
  align-items: center;
}
.github img {
  margin-left: 20px;
  width: 30px;
  height: 30px;
}
.github h5 {
  margin-left: 20px;
}
.footer {
  margin-top: -10px;
}

@media (max-width: 1150px) {
  .app-image {
    grid-column: 1/3;
    margin-left: 40px;
  }

  .title-container {
    grid-column: 3/5;
    margin-right: 20px;
  }

  .title {
    margin-top: 0px;
    margin-bottom: 50px;
  }
}

@media (max-width: 980px) {
  .app-image {
    height: 400px;
  }
}

@media (max-width: 800px) {
  .images {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .app-image {
    width: none;
    margin-left: 0px;
    max-width: 400px;
    object-fit: scale-down;
  }
  .main-container {
    height: 150vh;
  }
  .carousel {
    height: 120vh;
  }

  .slide {
    height: 110vh;
  }

  .title-container {
    margin: 0% 5%;
  }
}

@media (max-width: 610px) {
  .title-container {
    margin-right: 10%;
  }
  .title h1 {
    font-size: 2rem;
  }
  .app-image {
    width: none;
    height: none;
    max-height: 300px;
    max-width: 90vh;
    object-fit: scale-down;
  }
  .images {
    overflow: hidden;
  }
}

@media (max-width: 350px) {
  .app-image {
    max-height: 300px;
    max-width: 300px;
  }
}
</style>
