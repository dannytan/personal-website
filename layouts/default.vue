<template>
  <div>
    <SplashScreen></SplashScreen>
    <nuxt />
    <NavBar></NavBar>
  </div>
</template>

<script>
import SplashScreen from '~/components/SplashScreen'
import NavBar from '~/components/NavBar'

export default {
  components: {
    SplashScreen,
    NavBar
  },
  head () {
    return {
      title: 'Daniel Tan'
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@400;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono&display=swap');

html {
  font-family: 'Josefin Sans', sans-serif;
  font-size: 14px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
</style>
