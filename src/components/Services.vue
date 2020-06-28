<template>
    <div class="service" >

        
        <div class="heading">
             <h1>Services We Are Offering</h1>
        </div>

        <div class="service-container" >
     
         
                <div
                    class="service-holder"
                     v-for="(i,index) in services"
                    :key="index"
                >
                    <div class="image-container">
                        <img :src='i.image' alt="">
                    </div>
                    <div class="list-title-container">
                        <h4>{{i.title}}</h4>
                        <h6>{{i.subtitle}}</h6>
                    </div>
             </div>

            
        </div>

    </div>
</template>

<script>
export default {
    name:"Services",
    data(){
        return {
            services:[
                {
                    title:"App Development",
                    subtitle:"We specialise in native and cross-platform consumer apps, creating exceptional digital experience at every touch point.",
                    image:require("../assets/app.jpg")
                },

                {
                    title:"Web Development",
                    subtitle:"We work with the latest tech stacks to engineer front-end and back-end solutions.",
                    image:require("../assets/web.jpg")
                },
                {
                    title:"Software Development",
                    subtitle:"We build frontline software solutions that enable enterprises to unlock innovation and make a difference in the tech world",
                    image:require("../assets/desktop.jpg")
                },
                {
                    title:"Cloud & DevOps",
                    subtitle:"Our team creates flexible and agile environment using DevOps to meet business needs.",
                    image:require("../assets/cloud.jpg")
                },
                 {
                    title:"Blockchain Solutions",
                    subtitle:"Top-notch Blockchain developers, designers, and product owners - ready to build your product.",
                    image:require("../assets/eth.jpg")
                },
                
            ]
        }
    }
}
</script>

<style scoped>

  .service{
      min-height: 100vh;
      width: 100%;
      background-color: #fafafa;
      display: grid;
      grid-template-rows: 20% 80%;
  }

  .heading{
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      background-color: #fafafa;
      justify-content: center;
      text-align: center;
  }
  

  .heading h1,h5{
     margin: 0%;
  }
  .heading h5{
      margin-top: 10px;
      opacity: 0.4;
  }

  .service-container{
      height: 100%;
      background-color: #fafafa;
      display: grid;
      grid-template-columns: 30% 30% 30%;
      justify-content: space-around;
      row-gap: 50px;
      grid-template-rows: 30% 30% 30%;
     
  }

  .service-holder{
     background-color: white;
     border-radius: 1px;
     width: 100%;
     cursor: pointer;
     height: 100%;
     padding: 0%; 
     background: #ffffff;
     box-shadow:  20px 20px 60px #d9d9d9, 
             -20px -20px 60px #ffffff;
     overflow: hidden;
     display: grid;
     grid-template-columns: 30% 70%;
  }

   .service-holder:hover{
     cursor: pointer;
     box-shadow:  50px 50px 100px #d9d9d9, 
             -50px -50px 100px #ffffff;
   }

   .image-container{
       display: flex;
       height: 100%;
       width: 100%;
       justify-content: center;
       align-items: center;
   }

   .image-container img{
     max-width: 100%;
    max-height: 90%;
      margin-left: 10px;
      margin: auto;
      object-fit:scale-down;
   }

   .list-title-container{
       object-fit: scale-down; 
       margin-left:20px;
       display: flex;
       flex-direction: column;
       justify-content: center;
       align-items: flex-start;
       margin-right: 10px;
   }

   .list-title-container h4,h6{
       margin: 5px;
   }
   .list-title-container h6{
       margin: 5px;
       opacity: 0.6;
   }



   @media (max-width: 1040px) {
      .service-container{
        grid-template-columns: 45% 45%;
        grid-template-rows: 25% 25% 25%;
      }

   }

   @media (max-width: 750px) {
      .service{
            height: 165vh;
       }

      .service{
        grid-template-rows: 15% 85%;
      }

      .service-container{
        grid-template-columns: 90%;
        row-gap: 25px;
        grid-template-rows: 16% 16% 16% 16% 16% 16%;
      }

    .heading h1{
      font-size: 1.5rem;
      width: 80%;
    }

  

   }

    @media (max-width: 650px){
        .service-holder{
            pointer-events: none;
        }
        .list-title-container h4{
        font-size: 0.8rem;
        font-weight: bold;
        }
        .list-title-container h6{
        font-size: 0.6rem;
        }
    }
   

 

</style>