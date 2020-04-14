<template>
  <div class="splash-screen">
    <img id="shaka-splash" src="../assets/img/shaka-emoji.png" alt="Shaka Emoji">
  </div>
</template>

<script>
export default {
  name: 'SplashScreen'
}
</script>

<style lang="scss" scoped>
  .splash-screen {
    z-index: 3;
    background: #FF5475;
    position: fixed;
    width: 100%;
    height: 0;
    opacity: 0;

    animation: fade-out 3s /*infinite*/;
  }

  .splash-screen #shaka-splash {
    --size: 150px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    width: var(--size);

    animation: zoom-in 2s /*infinite*/;
    animation-delay: 1s;
  }

  @keyframes zoom-in {
    50% {
      width: var(--size);
    }
    60% {
      width: calc(var(--size) * 0.9);
    }
    100% {
      width: 250%;
    }
  }
  @keyframes fade-out {
    0%, 85% {
      opacity: 1;
      height: 100%;
    }
    99%{
      height : 100%;
    }
    100%{
      opacity : 0;
      height : 0;
    }
  }

  @-webkit-keyframes wiggle {
    0% {-webkit-transform: rotate(10deg);}
    25% {-webkit-transform: rotate(-10deg);}
    50% {-webkit-transform: rotate(20deg);}
    75% {-webkit-transform: rotate(-5deg);}
    100% {-webkit-transform: rotate(0deg);}
  }

  @-ms-keyframes wiggle {
    0% {-ms-transform: rotate(1deg);}
    25% {-ms-transform: rotate(-1deg);}
    50% {-ms-transform: rotate(1.5deg);}
    75% {-ms-transform: rotate(-5deg);}
    100% {-ms-transform: rotate(0deg);}
  }

  @keyframes wiggle {
    0% {transform: rotate(10deg);}
    25% {transform: rotate(-10deg);}
    50% {transform: rotate(20deg);}
    75% {transform: rotate(-5deg);}
    100% {transform: rotate(0deg);}
  }
</style>
