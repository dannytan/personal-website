<template>
  <div class="home">
    <div class="heart"></div>
    <img src="~/assets/img/home.png" alt="home" class="home-img"/>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      interval: null
    }
  },
  mounted () {
    this.interval = setInterval(() => {
      document.getElementsByClassName('home')[0].style.backgroundColor = 'rgba(' + this.createColor() + ',.4)'
    }, 500)
  },
  methods: {
    createColor () {
      return Math.round(245 * Math.random()) + ', ' + Math.round(245 * Math.random()) + ', ' + Math.round(245 * Math.random())
    }
  }
}
</script>

<style lang="scss" scoped>
  .home {
    min-height: 600px;
    height: 100vh;
    display: flex;
    background: rgba(155, 89, 182, 0.4);
    .title {
      display: block;
      font-weight: 300;
      font-size: 100px;
      color: #35495e;
      letter-spacing: 1px;
      margin-top: 50px;
    }
    .heart {
      z-index: 1;
      width: 40px;
      height: 40px;
      background: tomato;
      position: absolute;
      bottom: 342px;
      left: calc(50% + 20px);
      border-radius: 10%;
      animation: grow 0.7s ease infinite;
      transform: rotate(45deg);

      &:after {
        content: "";
        width: 40px;
        height: 40px;
        background: tomato;
        position: absolute;
        left: -20px;
        border-radius: 50%;
      }

      &:before {
        content: '';
        width: 40px;
        height: 40px;
        background: tomato;
        position: absolute;
        top: -20px;
        border-radius: 50%;
      }
    }
    .home-img {
      position: absolute;
      bottom: 0;
      left: 50%;
      margin-left: -425px;
      //min-height: 400px;
      //height: 80%;
      width: 850px;
    }

    @keyframes grow{
      50%{
        transform: scale(1.3) rotate(45deg);
      }
      100%{
        transform: scale(1) rotate(45deg);
      }
    }
  }
</style>
