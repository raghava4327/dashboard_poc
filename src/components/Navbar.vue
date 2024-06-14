<template>
    <div class="navbar flex poppins-medium ">
     <div class="flex gap-md items-center">   
    <FontAwesomeIcon :class="[icon-size]"  :icon="faBars"/>
    <FontAwesomeIcon :class="['light',icon-size]" :icon="faEnvelope" />
    <FontAwesomeIcon :class="['light',icon-size]" :icon="faBell" />
    <div class="flex gap-sm  items-center">
    <img class="flag-img" src="../assets/640px-Flag_of_the_United_Kingdom.svg.png" alt="" />
    <p>English</p>
</div>
</div>
<div class="flex gap-md  items-center" >
    <FontAwesomeIcon :class="['light',icon-size]" :icon="faSearch" />
    <div class="flex gap-sm  items-center">
    <FontAwesomeIcon :class="['light',icon-size]" :icon="faUser" />
    <p class="light">Raghava</p>
</div >
    <FontAwesomeIcon :class="['light',icon-size]" :icon="faComments" />
</div>
    </div>
  </template>
  
  <script>
  import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faBell, faComments, faEnvelope, faUser } from '@fortawesome/free-regular-svg-icons';
import { faBars, faSearch } from '@fortawesome/free-solid-svg-icons';
  
  export default {
    name: 'NavBar',
    components: {
      FontAwesomeIcon
    },
    data() {
      return {
        
        faEnvelope,
        faBars,
        faBell,
        faSearch,
        faUser,
        faComments
        
      }
    }
  }
  </script>
  
  <style scoped>
  .navbar {
    background-color: white;
    padding: 20px;
    justify-content: space-between;
   
    
  } 
 .items-center{
    align-items: center;
 }
  .flex{
    display: flex;

  }
  .gap-md{
    gap:20px;
  }
  .gap-sm{
    gap:10px;
  }
  .flag-img,icon-size{
    width:25px;
    height: 15px;
  }
  .light{
    color:rgba(172,166,161,255)
  }
  </style>
  