<template>
  <div class="contact">
    <main></main>
    <footer>
      <div class="logo">
        <img :src="logo" />
      </div>
      <div class="social-links">
        <div class="links" v-for="(i,index) in socialLinks" :key="index">
          <img :src="i.image" />
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      logo: require("../assets/logo-footer.svg"),
      socialLinks: [
        {
          image: require("../assets/social/linkedin.svg")
        },
        {
          image: require("../assets/social/insta.svg")
        },
        {
          image: require("../assets/social/whatsapp.svg")
        },
        {
          image: require("../assets/github.svg")
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
  box-shadow: 0 19px 38px rgba(0, 0, 0, 0.3), 0 15px 12px rgba(0, 0, 0, 0.22);
  z-index: 1;
  pointer-events: none;
  position: relative;
  background-color: white;
  height: 70vh;
}
footer {
  padding: 0%;
  width: 100%;
  bottom: 0px;
  height: 250px;
  z-index: -1;
  justify-content: center;
  align-items: center;
  display: flex;
  bottom: 0px;
  position: fixed;
  background: #c8a4fa;

  flex-direction: column;
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
</style>