<template>
  <nav class="nav">
    <div class="#logo">
      <nuxt-link :to="{name: 'index'}" class="logo couleur accent bold">
       C-64 "Client"
      </nuxt-link>
      <span class="subheader">Un projet de la cohorte au DEC intensif en informatique</span>
      <br>
      <a v-if="isLoggedIn" class="btn btn-danger"
      v-on:click="logout" >Se deconnecter</a>
    </div>
  </nav>
</template>

<script>
  export default {
    data() {
      return {     
        username: "",
        isLoggedIn: false
      }
    },

watch: {
  $route(){
    this.loggedIn()
  }
},
mounted(){
  this.loggedIn()
},

  methods: {   
    logout(){
      localStorage.removeItem("username");
      localStorage.removeItem("token");
      this.$router.push('login');
      this.isLoggedIn = false;
    },
    loggedIn(){
      this.isLoggedIn =!! localStorage.getItem("token");
      }

  }

  }
</script>

<style scoped>
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 70px;
    font-weight: lighter;
    letter-spacing: 0.5px;
  }
  .nav .logo {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .nav .logo .subheader {
    opacity: 0.70;
    font-size: 0.9rem;
    color: white;
  }
  .nav .nav-content {
    font-size: 1rem;
  }
  .nav-content ul {
    display: flex;
    list-style: none;
  }
  .nav-content ul li {
    padding: 2px 10px;
  }
  .nav-content ul li:not(:first-of-type) {
    border-left: 1px solid rgb(255, 255, 255, 0.2);
  }
</style>
