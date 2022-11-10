<template>
  <div>
    <Navbar />
    <Nuxt />
  </div>
  </template>

  <script>
    import { BIcon, BIconHouseDoorFill } from 'bootstrap-vue'
    import Navbar from '@/components/Navbar.vue';
    
    export default {
      components: {
        Navbar,
        BIcon,
        BIconHouseDoorFill
      }
    }
  </script>
  
  <style>
  html, body {
    background-color: #fff2f2;
    font-family: Volkorn
  }
  h1 {
    font-family: Satisfy
  }
  a {
  color: black;
  text-decoration: none;
}
a:hover {
  color: black;
  text-decoration: none;
}
  </style>
  