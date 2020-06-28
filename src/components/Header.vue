<template>
    <div class="header-container" >
        
       <vue-particles
        class="particles"
        color="#dedede"
        :particleOpacity="0.7"
        :particlesNumber="80"
        shapeType="circle"
        :particleSize="4"
        linesColor="#dedede"
        :linesWidth="2"
        :lineLinked="true"
        :lineOpacity="0.4"
        :linesDistance="200"
        :moveSpeed="3"
        :hoverEffect="true"
        hoverMode="grab"
        :clickEffect="true"
        clickMode="push"
      >
      </vue-particles>
      

       <nav
          class="navBar"
          v-bind:class="{scrolled:isScrolled}"
       >
          <div
             id="logo-container"
          >
             <div class="logo">
                 <img :src="logo" />
                 <div class="logo-title" >
                   <h4>{{title}}</h4>
                   <h6>{{subTitle}} </h6>
                 </div>
             </div>

          <div v-on:click="menuOpen()" class="hamburger">
               <div id="line1" class="line"></div>
               <div id="line2" class="line"></div>
               <div id="line3" class="line"></div>
          </div>
           
          </div>

          <div
             class="menu-container"
             :class="{menuOpen:isMenuOpen}"
          >
                 <div
                   v-on:click="scroll(0)"
                   :class="{selected:currentPage==1}"
                 >
                  <h5   >Home</h5>
                 </div>
                 <div
                   v-on:click="scroll(1)"
                   :class="{selected:currentPage==2}"
                 >
                  <h5  >Services</h5>
                 </div>
                 <div
                    v-on:click="scroll(windowHeight<=650?2.5:2)"
                   :class="{selected:currentPage==3}"
                 >
                   <h5 >Portfolio</h5>
                 </div>
                 <div
                    :class="{selected:currentPage==4}"
                     v-on:click="scroll(3)"
                 >
                 <h5>Contact</h5>
                 </div>
          </div>

       

       </nav>

       <div class="title-container">
           
           <h1>
               {{mainTitle}}
           </h1>

           <div class="subTitle-container">
               <p>
                   Full-cycle <mark>{{software}}</mark> & <mark>{{website}}</mark> development services designed to help your business grow
               </p>

           </div>


       </div>
       
    </div>
</template>

<script>
import Vue from 'vue'
import VueParticles from 'vue-particles'
Vue.use(VueParticles)


export default {
    
    mounted () {
       this.onScroll() 
       window.addEventListener('scroll', this.onScroll)
         window.addEventListener('resize', () => {
            this.windowHeight = window.innerHeight
        })
    },
    beforeDestroy () {
       window.removeEventListener('scroll', this.onScroll)
    },
    data(){
        return {
            backgroundImage : require("../assets/background.jpg"),
            logo:require("../assets/fire-512.png"),
            title:"DevAsh",
            subTitle:'Development & Solutions',
            mainTitle:"Hey There !",
            software:"{ Software }",
            website:"< Website />",
            isScrolled:false,
            currentPage:1,
            isMenuOpen:false,
            windowHeight:undefined
        }
    },
    methods:{
        scroll(size){
           if(this.isMenuOpen){
                this.isMenuOpen = false
                setTimeout(()=>{
                    let pageHeight = window.innerHeight;
                    window.scrollTo(0,size*pageHeight-50)
                },1000)
           }else{
               let pageHeight = window.innerHeight;
            window.scrollTo(0,size*pageHeight-50)
           }
           
   
          
        },
        menuOpen(){
            this.isMenuOpen=!this.isMenuOpen,
            console.log(this.isMenuOpen)
        },
        onScroll(){
            var scrollTop =
                (window.pageYOffset !== undefined) ? 
                     window.pageYOffset : 
                     (document.documentElement || document.body.parentNode || document.body).scrollTop;
            var section = document.body.scrollHeight/4
            if(scrollTop>section*3-150){
                 this.currentPage=4
            }else if(scrollTop>section*2-150){
                 this.currentPage=3
            }else if(scrollTop>section*1-150){
                 this.currentPage=2
            }else{
                 this.currentPage=1
            }
            
            if(scrollTop<10){
                this.isScrolled=false
            }else{
                this.isScrolled=true
            }
        }
    }
}
</script>

<style scoped>

  
    

   .header-container{
      height: 100vh;
      width: 100vw;
      background: linear-gradient(#000f14,#000f14,#001d27);
   }
   .particles{
     height: 100vh;
     position: absolute;
     z-index: 3;
      width: 100vw;
   }
   #image-cover{
       position: absolute;
       top: 0%;
      height: 100vh;
      width: 100vw;
       background-color:black;
       z-index: 2;
       opacity: 0.7;
   }

   .navBar{
       height: 70px;
       width: 100%;
       position: fixed;
       top: 0%;
       transition: 0.3s ease;
       display: grid;
       align-items: center;
       justify-content: center;
       grid-template-columns: 60% 40%;
       z-index: 3;
   }

     .line{
        width: 30px;
        height: 2.5px;
        background: white;
        margin: 5px;
    }


    
    .hamburger{
        display: none;;
        right: 10px;
        position: absolute;
        cursor: pointer;
    }

   .logo-container{
       display: flex;
       justify-content: center;
       align-items: center;
   }

   .logo{
       height: 45px;
       width: 190px;
       display: flex;
       align-items: center;
       border-radius: 60px;
       box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
       background-color: #ffc400;
       margin-left: 20px;
   }

   .logo img{
       height: 30px;
       width: 30px;
       margin-left: 10px;
   }

   .logo-title{
       display: flex;
       flex-direction:column ;
       justify-content: center;
       align-items: flex-start;
       margin-left: 15px;
       height: 100%;
       margin-bottom: 2px;
   }

   .logo h4 , h6{
       margin: 0%;
   }

   .logo h6{
       margin: 0%;
       font-size: 8px;
       opacity: 0.8;
   }

   .menu-container {
     display: flex;
     flex-direction: row;
     color: white;
   }

   .menu-container h5 {
     display: flex;
     opacity: 0.8;
     padding: 5px 0px;
     flex-direction: row;
     color: white;
     margin: 0% 30px;
   }

   .menu-container .selected{
     border-bottom:solid 0.5px #ffc400;
   }


   .menu-container :hover {
       cursor: pointer;
       opacity: 1;
   }

   .title-container{
       width: 100%;
       height: 100%;
       text-align: center;
       z-index: 2;
       display: flex;
       flex-direction:column;
       justify-content: center;
       align-items: center;
       top: 0%;
       position: absolute;
   }

   .title-container h1{
       color: white;
       opacity: 0.8;
       margin: 0%;
       font-size: 3rem;
   }
    .title-container h4{
       color: white;
       opacity: 0.8;
       font-size: 2rem;
    }
    .subTitle-container p{
       color: white;
       opacity: 0.8;
       text-align: center;
   }

   .subTitle-container{
      width: 500px;
   }

   .scrolled{
       background-color: rgba(0, 0, 0, 1) ;
       box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
   }

   mark{
       background: transparent;
       color: #ffc400;
   }

   @media (max-width: 1040px) {
       .navBar{
           grid-template-columns: 50% 50%;
       }
   }

    @media (max-width: 820px) {
       .menu-container{
           display: flex;
           flex-direction: column;
           justify-content: center;
           align-items: center;
           width: 100%;
           position: absolute;
           top: 0%;
           z-index: -1;
           background-color: rgba(0, 0, 0, 1) ;
           box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
           padding-top:80px ;
           transition: all 1s ease-out;
           clip-path: circle(100px at 100% -50%);     
       }


      .menuOpen{
          clip-path: circle(1000px at 90% 10%);  
       }
      
       .menu-container div{
           padding: 10px;
           width: 100%;
           border-bottom: solid 0.1px #202020;
           display: flex;
           align-items: center;
           justify-content: center;
       }

        .menu-container .selected{
            color:  #ffc400;
            border-bottom: solid 0.1px #202020;
            
        }

         .menu-container .selected>h5{
            color:  #ffc400;
            
        }
      
      
       #logo-container{
           display: flex;
           align-items: center;
           justify-content: space-between;
       }

       .navBar{
           display: flex;
           justify-content: center;
           flex-direction: column;
           align-items: flex-start;
       }

       

       
     .hamburger{
        display: inline;
     }
   }

    @media (max-width: 600px) {
     .subTitle-container{
          width: 95%;
      }

    .title-container h1{
        font-size: 2rem;
    }

   }

</style>