<template>
  <div id="app">
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="#"><router-link to="/">Home</router-link> </b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item> <router-link to="/numerosprimos">Calcula números primos</router-link> </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <router-view/>
  </div>
</template>


<script>
export default {
  name:'Navbar'

}
</script>



<style>
#app > nav > a > a { 
  color: red;
  text-decoration: none;
  margin-left: 10px ;
}
#nav-collapse > ul > li > a > a {
  color: chocolate ;
  text-decoration: none;
}

</style>
