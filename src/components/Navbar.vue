<template>
   <div id="nav">
      <div id="header">
         <img src="../assets/logo.png" height="30" width="30">
         Vue Converter 
      </div>
      <a v-for="quantity in quantities" 
         v-bind:key="quantity.name" 
         @click="$emit('select-quantity',quantity)" >
         {{quantity.name}}
      </a> 
   </div>
</template>

<script>
export default {
  name:'Navbar',
  data(){
      return{
         quantities: [
            {name:"Length", units:["mm","cm","m"]},
            {name:"Temperature", units:["C","K","F"]},
            {name:"Time", units:["s","min","h"]}
         ]
      }
  },
  methods:{
   /* no methods yet */
  }
}
</script>

<style scoped>
    #nav{
        display:flex;
        flex-direction:column;
        height:100vh;
        width:20vw;
        background-color:rgb(53, 73, 94);
        color:white;
    }
    #nav>div{
        display:flex;
        flex-direction:column;
        justify-content:center;
        align-items:center;
        padding:20px 0 20px 0;
        text-align:Center;
        vertical-align:middle;
    }
    #header>img{
       background-color:white;
       padding:10px;
       border-radius:20%;
       margin: 5px;
    }
    a{
       text-align:center;
       padding:20px;
       background-color:rgb(77, 186, 135);
       transition:background-color 0.5s;
       cursor:pointer;
    }
    a:hover{
        background-color:rgb(57, 166, 125);
    }
    #footer{
        height:15vh;
        background-color:rgb(33, 53, 74);
        margin-top:auto;  /* places the footer at the end of the navbar */
        box-sizing:border-box;
        padding:15px;
        font-size:0.8em;
    }
</style>