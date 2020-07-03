<template>
  <div class="about">
    <div class="content">
      <h1>
        Hi, I’m
        <mark>Ashwin</mark>
      </h1>
      <div class="image">
        <img :src="myImage" />
      </div>
      <p>Since beginning my journey as a freelance developer nearly 2 years ago, I've done remote work for agencies, consulted for startups, and collaborated with talented people to create digital products for both business and consumer use.</p>
      <div class="underline"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myImage: require("../assets/mypic.jpg")
    };
  }
};
</script>

<style scoped>
.about {
  height: 80vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  max-width: 700px;
  margin: 0px 30px;
}
.content p {
  text-align: center;
  font-size: 1.2rem;
  margin: 0px;
  opacity: 0.7;
}

.content h1 {
  font-size: 3rem;
  cursor: pointer;
}

.underline {
  height: 2px;
  width: 60px;
  margin-top: 60px;
  background-color: #fb397d;
}

mark {
  background: transparent;
  color: black;
}

.image img {
  height: 150px;
  width: 150px;
  overflow: hidden;
  margin: 50px 0px;
  border-radius: 50%;
  cursor: pointer;
  padding: 5px;
  box-shadow: 20px 20px 60px #d9d9d9, -20px -20px 60px #ffffff;
}

@media (max-width: 500px) {
  .content h1 {
    font-size: 2rem;
  }
  .content p {
    font-size: 1.1rem;
  }

  .underline {
    margin-top: 30px;
  }

  .about {
    height: 90vh;
  }
}
</style>