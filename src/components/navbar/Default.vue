<template>
  <b-navbar toggleable="md" type="dark" class="dark">
    <div class="container">
      <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

      <b-navbar-brand href="#"><img class="nav-img" src="/static/img/nano.png"> API.ONLINE</b-navbar-brand>

      <b-collapse is-nav id="nav_collapse">

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">

          <b-nav-item href="#tuto">{{tutorials}}</b-nav-item>
          <b-nav-item href="#docs">{{docs}}</b-nav-item>
          <b-nav-item href="#donate">{{donate}}</b-nav-item>
          <b-nav-item href="#">{{server}}</b-nav-item>

          <b-nav-item-dropdown no-caret :text="'<img src='+langicon+' class=´asd´>'" right>
            <b-dropdown-item href="#">PT</b-dropdown-item>
            <b-dropdown-item href="#">EN</b-dropdown-item>
          </b-nav-item-dropdown>
        </b-navbar-nav>

      </b-collapse>
     </div>
  </b-navbar>
</template>
<script>
export default {
  name: 'NavbarDefault', 
  data () {
    return {
      tutorials: 'Tutoriais',
      docs: 'Documentação',
      donate: 'Colabore',
      server: 'Servidor',
      langicon: 'http://nanoapi.online/img/icons/brflag.png'
    }
  }
}
</script>

<style scoped>
  .dark{
    font-family: 'Montserrat';
    background-color: #2C3E50;
  }
	.nav-img{
		width: 36px;
	}
</style>
