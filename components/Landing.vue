<template>
  <div class="landing">
    <div class="title-wrapper">
      <div class="title" :class="$mq">
        DANIEL TAN
      </div>
      <div class="sub-title">
        Developer // Drummer
      </div>
      <el-button class="enter-button">
        ENTER
      </el-button>
    </div>
    <div class="heart"></div>
    <img src="~/assets/img/home.png" alt="home" class="home-img"/>
    <NavBar></NavBar>
  </div>
</template>

<script>
import NavBar from '~/components/NavBar'

export default {
  name: 'Landing',
  components: {
    NavBar
  },
  data () {
    return {
      interval: null
    }
  },
  mounted () {
    this.interval = setInterval(() => {
      document.getElementsByClassName('landing')[0].style.backgroundColor = 'rgba(' + this.createColor() + ',.4)'
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
  .landing {
    min-height: 800px;
    height: 100vh;
    position: relative;
    overflow: hidden;
    background: rgba(155, 89, 182, 0.4);
    .title-wrapper {
      text-align: center;
      padding-top: 90px;
      .title {
        color: rgba(255, 255, 255, 0.8);
        font-size: 64px;
        &.xs {
          font-size: 42px;
        }
      }
      .sub-title {
        color: rgba(255, 255, 255, 0.8);
        font-size: 22px;
      }
      .enter-button {
        margin-top: 15px;
        font-size: 20px;
        font-weight: bold;
        background: transparent;
        color: rgba(255, 255, 255, 0.8);
        border: 2px solid rgba(255, 255, 255, 0.8);
        &:hover {
          color: tomato;
          background: rgba(255, 255, 255, 0.8);
        }
      }
    }
    .heart {
      z-index: 1;
      width: 40px;
      height: 40px;
      background: tomato;
      position: absolute;
      bottom: 360px;
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
      bottom: 80px;
      left: 50%;
      margin-left: -375px;
      margin-bottom: -7px;
      width: 750px;
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
