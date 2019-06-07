<template>
  <div id="app">
   <Navbar @select-quantity="chosenQuantity=$event"/>  
   <Converter v-bind:physicalQuantity="chosenQuantity"/> 
  </div> 
</template>

<script>
import Navbar from './components/Navbar.vue'
import Converter from './components/Converter.vue'

export default {
  name: 'app',
  components: {
    Converter,
    Navbar
  },
  data: function(){
    return{
      chosenQuantity: {name:"Time",id:2, units:["s","min","h"]}         /* the currently chosen quantity. Per default, the chosen quantity is TIME */
    }
  }
}
</script>

<style>
body{
  margin:0;
  font-family:"Source Sans Pro";
}
#app{
  display:flex;
}
</style>
