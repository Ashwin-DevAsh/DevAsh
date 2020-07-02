<template>
  <div class="about">
    <div class="content">
      <h1>Hi, I’m Ashwin</h1>
      <div class="image">
        <img :src="myImage" />
      </div>
      <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Incidunt expedita tenetur cupiditate? Soluta sint numquam porro ullam fuga libero dicta repellat dolor, maxime nobis ab impedit consequatur assumenda, distinctio consectetur.</p>
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
}

.underline {
  height: 2px;
  width: 60px;
  margin-top: 60px;
  background-color: #fb397d;
}

.image img {
  height: 150px;
  width: 150px;
  overflow: hidden;
  margin: 50px 0px;
  border-radius: 50%;

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