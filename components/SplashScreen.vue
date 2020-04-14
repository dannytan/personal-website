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
    background: #FFFFFF;
    position: fixed;
    width: 100%;
    height: 0;
    opacity: 0;

    animation: fade-out 2s /*infinite*/;
  }

  .splash-screen #shaka-splash {
    --size: 180px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    width: var(--size);

    animation: wiggle 1s, zoom-in 2s /*infinite*/;
  }

  @keyframes zoom-in {
    50% {
      width: var(--size);
    }
    60% {
      width: calc(var(--size) * 0.9);
    }
    100% {
      width: 400%;
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

  @keyframes wiggle {
    0% {transform: translate(-50%, -50%) rotate(10deg);}
    25% {transform: translate(-50%, -50%) rotate(-10deg);}
    50% {transform: translate(-50%, -50%) rotate(20deg);}
    75% {transform: translate(-50%, -50%) rotate(-5deg);}
    100% {transform: translate(-50%, -50%) rotate(0deg);}
  }
</style>
