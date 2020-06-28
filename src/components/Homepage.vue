<template>
    <div>
       <Header></Header>
       <Services></Services>
       <div style="height:100vh;background:red" ></div>
       <div style="height:100vh" ></div>
    </div>
</template>

<script>
import Header from '../components/Header'
import Services from '../components/Services'
export default {
    name:'Homepage',
    components:{
        Header,
        Services
    }
}
</script>

<style scoped>
  
</style>

