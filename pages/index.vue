<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        Client-C64
      </h1>
       <nuxt-link :to="{name: 'login'}" class="button--grey">
        Login
        </nuxt-link> 
        <a
          href="https://github.com/CVM-C64-H2021/Client"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
    </div>
  </div>
</template>

<script>

export default {
  
}




</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
  'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
}
.links {
  padding-top: 15px;
}
</style>
