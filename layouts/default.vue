<template>
  <client-only>
  <div >
    <div  :class="$route.name == 'index' ? '':' navbarsec' ">
    <b-navbar class="navbar header container" >
        <template slot="brand">
          <b-navbar-item tag="router-link" :to="{ path: '/' }">
            <!-- <img src="~assets/index.png" alt height="28" /> -->
            <h1 class="brandname">Court</h1>
          </b-navbar-item>
        </template>
        <template slot="end">
          <b-navbar-item>

              <nuxt-link to="/" class="navbar-item"> Home</nuxt-link>
          </b-navbar-item>
          <b-navbar-item>
            <nuxt-link to="/about" class="navbar-item"> About us</nuxt-link>
          </b-navbar-item>
          <b-navbar-dropdown label="Register">
            <b-navbar-item>
              <nuxt-link to="/lawreg" class="navbar-item">Lawyer</nuxt-link>
            </b-navbar-item>
            <b-navbar-item>
              <nuxt-link to="/clientreg" class="navbar-item">Client</nuxt-link>
            </b-navbar-item>
          </b-navbar-dropdown>
               <b-navbar-item>

              <nuxt-link to="/log" class="navbar-item"> Log in</nuxt-link>
          </b-navbar-item>
      
        </template>
   
        <div>
          <b-navbar-item>My Profile</b-navbar-item>

          <b-navbar-dropdown label="Case Form">
            <b-navbar-item>Criminal Case</b-navbar-item>
            <b-navbar-item>Civil Case</b-navbar-item>
          </b-navbar-dropdown>
          <b-navbar-item>Solution For Case</b-navbar-item>
          <b-navbar-dropdown label="List of Lawyer">
            <b-navbar-item>sudhan</b-navbar-item>
            <b-navbar-item>hari</b-navbar-item>
          </b-navbar-dropdown>
          <template slot="end">
            <div class="buttons">Log out</div>
          </template>
        </div>
        <div>
          <b-navbar-item>My Profile</b-navbar-item>

        <b-navbar-dropdown label="Public Case">
            <b-navbar-item>Criminal Case</b-navbar-item>
            <b-navbar-item>Civil Case</b-navbar-item>
          </b-navbar-dropdown>
          <b-navbar-item>My Cases</b-navbar-item>

          <template slot="end">
            <div class="buttons">Log out</div>
          </template>
       
      </div>

      
    </b-navbar>
  </div>

    <nuxt />
<footer>
  <p class="has-text-white has-text-centered">Copyright © 120 SystimaNX IT solutions Pvt Ltd. All rights reserved. </p>
</footer>
  </div>
  </client-only>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

         
             

