<template>
 
  <nav style="background-color: rgb(157, 201, 201);">
    
      <strong>E-Grocery</strong>
    <img src="1.png" style="height: 60px; margin-right: 970px;" >
 
    <router-link to="/"> Home </router-link>  |
    <router-link to="/Products"> Products   </router-link>  |
    <router-link to="/about"> About Us      </router-link>  |
    <router-link to="/Contact"> Contact Us    </router-link>
  
  </nav>
</template>

<script>
export default {};
</script>

<style>
nav {
  padding: 10px;
  margin-top: 10px;
}

nav a {
  font-weight: bold;
  color: #080809;
  
}

nav a.router-link-exact-active {
  color: #36a774;
}
</style>