<template>
  <div class="contact">
    <div class="page5"></div>

    <header>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#884bdf"
          fill-opacity="1"
          d="M0,160L24,138.7C48,117,96,75,144,58.7C192,43,240,53,288,74.7C336,96,384,128,432,154.7C480,181,528,203,576,224C624,245,672,267,720,245.3C768,224,816,160,864,160C912,160,960,224,1008,234.7C1056,245,1104,203,1152,160C1200,117,1248,75,1296,74.7C1344,75,1392,117,1416,138.7L1440,160L1440,320L1416,320C1392,320,1344,320,1296,320C1248,320,1200,320,1152,320C1104,320,1056,320,1008,320C960,320,912,320,864,320C816,320,768,320,720,320C672,320,624,320,576,320C528,320,480,320,432,320C384,320,336,320,288,320C240,320,192,320,144,320C96,320,48,320,24,320L0,320Z"
        />
      </svg>
    </header>
    <main>
      <div class="logo">
        <img :src="logo" />
      </div>
      <h2>Living, learning, & leveling up one day at a time.</h2>
      <div class="social-links">
        <div class="links" v-for="(i,index) in socialLinks" :key="index">
          <a :href="i.link" target="_blank">
            <img :src="i.image" />
          </a>
        </div>
      </div>
      <h4>Handcrafted by Me © DevAsh</h4>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      logo: require("../assets/logo.svg"),
      socialLinks: [
        {
          image: require("../assets/social/linkedin.svg"),
          link: "https://www.linkedin.com/in/ashwin-r-a7234017a"
        },
        {
          image: require("../assets/social/insta.svg"),
          link: "https://www.instagram.com/_ash_win___/"
        },
        {
          image: require("../assets/social/whatsapp.svg"),
          link: "https://wa.me/919551574355"
        },
        {
          image: require("../assets/github.svg"),
          link: "https://www.github.com/Ashwin-DevAsh"
        }
      ]
    };
  }
};
</script>

<style scoped>
.contact {
  margin-top: -10px;
  overflow: hidden;
  display: flex;
  position: relative;

  height: 100vh;
  justify-content: space-between;
  flex-direction: column;
}
main {
  background: linear-gradient(#884bdf, #5e56e9);
  height: 100%;
  width: 100%;
  color: white;
  display: flex;
  align-items: center;
  margin-top: -20px;
  flex-direction: column;
  justify-content: center;
}

main h2 {
  max-width: 400px;
  text-align: center;
  opacity: 0.6;
  margin: 0px 20px;
}

main h4 {
  opacity: 0.4;
}

.wave {
  display: flex;
  flex-direction: column;
}

.social-links {
  margin-top: 20px;
  display: flex;
}

.logo img {
  height: 100px;
  width: 100px;
  object-fit: scale-down;
}

.links {
  margin: 10px;
  width: 30px;
  height: 30px;
  display: flex;
  padding: 5px;
  justify-content: center;
  align-items: center;
  border-radius: 10px 10px 0px 10px;
  background: #5d28a7;
  cursor: pointer;
  transition: all 0.5s ease;
}

.links:nth-child(2) {
  background: #fb397d;
}

.links:hover {
  background: #fb397d;
}

.links img {
  height: 20px;
}

a {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-style: none;
  color: white;
}
</style>