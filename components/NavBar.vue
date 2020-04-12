<template>
  <nav :class="$mq">
    <ul>
      <li :class="{ active: isHomeActive }" @click="goTo('/')">
        <i v-if="isMobile" class="el-icon-house"></i>
        <span v-else>HOME</span>
      </li>
      <li :class="{ active: isAboutActive }" @click="goTo('/about')">
        <i v-if="isMobile" class="el-icon-user"></i>
        <span v-else>ABOUT</span>
      </li>
      <li :class="{ active: isWorksActive }" @click="goTo('/works')">
        <i v-if="isMobile" class="el-icon-suitcase"></i>
        <span v-else>WORKS</span>
      </li>
      <li :class="{ active: isBlogActive }" @click="goTo('/blog')">
        <i v-if="isMobile" class="el-icon-edit-outline"></i>
        <span v-else>BLOG</span>
      </li>
      <li :class="{ active: isContactActive }" @click="goTo('/contact')">
        <i v-if="isMobile" class="el-icon-message"></i>
        <span v-else>CONTACT ME</span>
      </li>
      <li class="slide"></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  computed: {
    isMobile () {
      return this.$mq === 'xs'
    },
    activeTab () {
      return this.$route.path
    },
    isHomeActive () {
      return this.activeTab === '/'
    },
    isAboutActive () {
      return this.activeTab === '/about'
    },
    isWorksActive () {
      return this.activeTab === '/works'
    },
    isBlogActive () {
      return this.activeTab === '/blog'
    },
    isContactActive () {
      return this.activeTab === '/contact'
    }
  },
  methods: {
    goTo (path) {
      this.$router.push(path)
    }
  }
}
</script>

<style lang="scss" scoped>
  nav {
    z-index: 2;
    width: 100%;
    background-color: #fff;
    position: fixed;
    bottom: 0;
    height: 80px;
    overflow: hidden;
    box-shadow: 0 0 9px 2px rgba(41 ,41, 41, 0.2);
    &.xs {
      height: 60px;
      li {
        height: 58px;
        line-height: 60px;
        font-size: 24px;
      }
    }
  }
  nav ul {
    position: absolute;
    top: 0;
    left: 0;
    list-style-type: none;
    padding: 0;
    margin: 0;
    width: 140vw;
  }
  nav li {
    float: left;
    display: inline-block;
    height: 78px;
    margin: 0 0 2px;
    line-height: 80px;
    width: 20vw;
    text-align: center;
    color: black;
    transition: background-color 0.5s 0.2s ease, color 0.3s ease;
    cursor: pointer;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 4px;
    font-weight: 800;
    transform: translateY(100%);
  }
  nav li.active {
    // background-color: #151515;
    color: tomato;
  }
  nav li.active::after {
    content: "";
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 100%;
    height: 2px;
    background-color: tomato;
  }
  nav li:nth-child(1) {
    animation: pop 0.5s 0.15s 1 forwards;
  }
  nav li:nth-child(2) {
    animation: pop 0.5s 0.3s 1 forwards;
  }
  nav li:nth-child(3) {
    animation: pop 0.5s 0.45s 1 forwards;
  }
  nav li:nth-child(4) {
    animation: pop 0.5s 0.6s 1 forwards;
  }
  nav li:nth-child(5) {
    animation: pop 0.5s 0.75s 1 forwards;
  }
  nav li:nth-child(6) {
    animation: pop 0.5s 0.9s 1 forwards;
  }
  nav li:nth-child(7) {
    animation: pop 0.5s 1.05s 1 forwards;
  }
  nav li:hover {
    color: tomato;
  }
  nav li:active {
    background-color: #fff;
  }
  nav li:nth-child(1):hover ~ .slide {
    left: 0;
  }
  nav li:nth-child(2):hover ~ .slide {
    left: 20vw;
  }
  nav li:nth-child(3):hover ~ .slide {
    left: 40vw;
  }
  nav li:nth-child(4):hover ~ .slide {
    left: 60vw;
  }
  nav li:nth-child(5):hover ~ .slide {
    left: 80vw;
  }
  nav li:nth-child(6):hover ~ .slide {
    left: 100vw;
  }
  nav li:nth-child(7):hover ~ .slide {
    left: 120vw;
  }
  nav li.slide {
    position: absolute;
    left: -20vw;
    top: 0;
    background-color: tomato;
    z-index: -1;
    height: 3px;
    margin-top: 77px;
    transition: left 0.3s ease;
    transform: translateY(0);
  }

  @-moz-keyframes pop {
    0% {
      transform: translateY(100%);
    }
    100% {
      transform: translateY(0);
    }
  }
  @-webkit-keyframes pop {
    0% {
      transform: translateY(100%);
    }
    100% {
      transform: translateY(0);
    }
  }
  @-o-keyframes pop {
    0% {
      transform: translateY(100%);
    }
    100% {
      transform: translateY(0);
    }
  }
  @keyframes pop {
    0% {
      transform: translateY(100%);
    }
    100% {
      transform: translateY(0);
    }
  }
</style>
