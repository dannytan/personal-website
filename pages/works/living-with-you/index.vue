<template>
  <div class="works-living-with-you" :class="$mq">
    <div class="title">
      Living with You
    </div>
    <div class="sub-title">
      <i>Living with You</i> is a single written and sung by Kolomona Ku, a talented artist from Hawai'i and now based in LA. I am featured playing the drums for the single, which can be found <a href="https://open.spotify.com/track/4IcYuuikfr884CjtXy3P9I?si=Ry2Ek_UrQQWJbwI5YuPtYA" target="_blank"><b>here</b></a>.
    </div>
    <br/>
    <div class="embed-container">
      <iframe src="https://open.spotify.com/embed/album/6s5p6ZKbNuRFJCdob7OSGZ" allowtransparency="true"></iframe>
    </div>
    <div class="description">
      The song was recorded and mixed by Imua Garza @ <a href="https://www.imuagarza.com/" target="_blank"><b>Zeo Music</b></a>.
    </div>
  </div>
</template>

<script>
export default {
  name: 'LivingWithYou'
}
</script>

<style lang="scss" scoped>
.works-living-with-you {
  font-family: 'Roboto Mono', monospace;
  padding: 8% 15% calc(8% + 80px) 15%;
  .title {
    font-size: 52px;
    font-weight: bold;
    margin-bottom: 20px;
  }
  .sub-title {
    font-size: 22px;
    line-height: 1.3;
  }
  .description {
    font-size: 18px;
    line-height: 1.3;
  }
  .embed-container {
    position: relative;
    overflow: hidden;
    max-width: 100%;
    height: 80px;
    margin-bottom: 20px;
  }
  .embed-container iframe,
  .embed-container object,
  .embed-container embed {
    border: 0;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  a {
    color: inherit;
    text-decoration: none;
  }
  &.md {
    padding: 8% 10% calc(8% + 80px) 10%;
  }
  &.sm {
    padding: 8% 8% calc(8% + 80px) 8%;
    .works-img {
      width: 100%;
    }
  }
  &.xs {
    padding: 8% 5% calc(8% + 80px) 5%;
    .title {
      font-size: 36px;
    }
    .sub-title {
      font-size: 18px;
    }
    .description {
      font-size: 16px;
    }
    .works-img {
      width: 100%;
    }
  }
}
</style>
