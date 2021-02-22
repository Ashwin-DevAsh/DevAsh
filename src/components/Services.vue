<template>
  <div class="service">
    <div style="margin-top:-70px" class="page2"></div>

    <div class="heading">
      <h1>Services We Are Offering</h1>
      <div class="underline"></div>
    </div>

    <div class="service-container">
      <div
        class="service-holder"
        :class="{'shake-animation':index==shakeThis}"
        v-for="(i, index) in services"
        :key="index"
      >
        <div class="image-container">
          <img :src="i.image" alt />
        </div>
        <div class="list-title-container">
          <h4>{{ i.title }}</h4>
          <h6>{{ i.subtitle }}</h6>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Services",
  mounted() {
    // this.shake();
  },
  methods: {
    shake() {
      let that = this;
      setInterval(function() {
        that.shakeThis =
          Math.floor(Math.random() * (that.services.length - 0 + 1)) + 0;
        setTimeout(() => {
          that.shakeThis = undefined;
        }, 1000);
      }, 5000);
    }
  },
  data() {
    return {
      shakeThis: undefined,

      services: [
        {
          title: "App Development",
          subtitle:
            "We specialise in native and cross-platform consumer apps, creating exceptional digital experience at every touch point.",
          image: require("../assets/app.svg")
        },

        {
          title: "Web Development",
          subtitle:
            "We work with the latest tech stacks to engineer front-end and back-end solutions.",
          image: require("../assets/web.svg")
        },
        {
          title: "Software Development",
          subtitle:
            "We build frontline software solutions that enable enterprises to unlock innovation and make a difference in the tech world",
          image: require("../assets/desktop.svg")
        },
        {
          title: "Cloud & DevOps",
          subtitle:
            "Our team creates flexible and agile environment using DevOps to meet business needs.",
          image: require("../assets/cloud.svg")
        },
        {
          title: "Blockchain Solutions",
          subtitle:
            "Top-notch Blockchain developers, designers, and product owners - ready to build your product.",
          image: require("../assets/eth.svg")
        }
      ]
    };
  }
};
</script>

<style scoped>
.service {
  margin-top: -80px;
  width: 100%;
  display: grid;
}

.heading {
  text-align: center;
  display: flex;
  height: auto;
  height: 200px;
  margin: 50px 0;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.underline {
  height: 2px;
  width: 60px;
  margin-top: 20px;
  background-color: #fb397d;
}

.heading h1,
h5 {
  z-index: 2;
  margin: 0%;
}
.heading h1 {
  font-size: 2.5rem;
}
.heading h5 {
  margin-top: 10px;
  opacity: 0.4;
}

.service-container {
  height: 100%;
  display: grid;
  grid-template-columns: 40% 40%;
  justify-content: space-around;
  row-gap: 50px;
  margin-bottom: 100px;
  grid-auto-rows: 250px;
}

.service-holder {
  background-color: white;
  border-radius: 1px;
  width: 100%;
  cursor: pointer;
  height: 100%;
  padding: 0%;
  background: #ffffff;
  border-top-right-radius: 40px;
  border-bottom-left-radius: 40px;
  /* box-shadow: 20px 20px 60px #d9d9d9, -20px -20px 60px #ffffff; */
  overflow: hidden;
  display: grid;
  grid-template-columns: 30% 70%;
}

.shake-animation {
  /* Start the shake animation and make the animation last for 0.5 seconds */
  animation: shake 0.5s;
  /* When the animation is finished, start again */
  animation-iteration-count: infinite;
}

@keyframes shake {
  0% {
    transform: translate(1px, 1px) rotate(0deg);
  }
  10% {
    transform: translate(-1px, -2px) rotate(-5deg);
  }
  20% {
    transform: translate(-3px, 0px) rotate(5deg);
  }
  30% {
    transform: translate(3px, 2px) rotate(5deg);
  }
  40% {
    transform: translate(1px, -1px) rotate(5deg);
  }
  50% {
    transform: translate(-1px, 2px) rotate(-5deg);
  }
  60% {
    transform: translate(-3px, 1px) rotate(0deg);
  }
  70% {
    transform: translate(3px, 1px) rotate(-5deg);
  }
  80% {
    transform: translate(-1px, -1px) rotate(5deg);
  }
  90% {
    transform: translate(1px, 2px) rotate(0deg);
  }
  100% {
    transform: translate(1px, -2px) rotate(-5deg);
  }
}

.image-container {
  display: flex;
  height: 100%;
  width: 100%;
  margin-left: 10px;
  justify-content: center;
  align-items: center;
}

.image-container img {
  max-width: 90%;
  max-height: 90%;
  margin: auto;
  object-fit: scale-down;
}

.list-title-container {
  object-fit: scale-down;
  margin-left: 20px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  margin-right: 10px;
}

.list-title-container h4,
h6 {
  margin: 5px;
}
.list-title-container h6 {
  margin: 5px;
  line-height:20px;
  opacity: 0.6;
}

@media (max-width: 1040px) {
  .service-container {
    grid-template-columns: 45% 45%;
  }
}

@media (max-width: 750px) {
  .service {
    margin-top: -50px;
  }
  .service-container {
    grid-template-columns: 90%;
    row-gap: 25px;
  }

  .heading h1 {
    font-size: 2rem;
    width: 80%;
  }
}
</style>
