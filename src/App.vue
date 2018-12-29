<template>
  <div id="app">
    <navbar-default/>
    <router-view/>
  </div>
</template>

<script>
import NavbarDefault from '@/components/navbar/Default';;

export default {
  name: 'App',
  components:{
    NavbarDefault
  }
}
</script>

<style>
  #app {
    font-family: 'Lato', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-weight: 700;
    font-family: 'Montserrat';
    text-transform: uppercase;
  }
  h1{
    font-size: 1.5rem;
  }
  h3{
    font-size: 1.2rem;
  }
  @media (min-width: 992px) {
    h1{

    }
  }
</style>
