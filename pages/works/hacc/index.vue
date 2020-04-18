<template>
  <div class="works-dismango" :class="$mq">
    <div class="title">
      HACC 2017
    </div>
    <div class="sub-title">
      I entered the <a href="https://hacc.hawaii.gov/" target="_blank"><b>Hawaii Annual Code Challenge</b></a> in 2017 and our team won first place overall! We built an app to improve navigating around the University of Hawai'i at Mānoa campus.
    </div>
    <br/>
    <div class="description">
      Click <a href="https://github.com/hacc17/lovemilktea" target="_blank"><b>here</b></a> to view the GitHub page and source code. Also, check out our demo video below!
    </div>
    <div class="media-content">
      <iframe
        class="works-video"
        width="806"
        height="569"
        src="https://www.youtube.com/embed/wLuSS2579hc"
        frameborder="0"
        allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      ></iframe>
    </div>
    <div class="description">
      Our team, consisting of 7 UH students at the time, spent a month hacking away to build this app. In order to develop something for both web and native devices in a short amount of time, we ended up using <a href="https://ionicframework.com/#" target="_blank"><b>Ionic</b></a>, a cross-platform framework. Personally, I think it worked great for what we were set out to accomplish, but I believe web and native apps should be developed separately in most cases, at least on the frontend.
    </div>
    <br/>
    <div class="img-wrapper">
      <img src="../../../assets/img/works/hacc-winner.jpg" class="works-img" />
    </div>
    <div class="img-wrapper">
      <img src="../../../assets/img/works/hacc-judges.jpg" class="works-img" />
    </div>
    <div class="description">
      If you are interested in reading more about our application and experience in this hackathon, check out our full <a href="https://devpost.com/software/ho-okele" target="_blank"><b>DevPost</b></a>.
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dismango'
}
</script>

<style lang="scss" scoped>
.works-dismango {
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
  .media-content {
    text-align: center;
    margin: 30px 0;
    overflow: hidden;
    padding-bottom: 56.25%;
    position: relative;
    height: 0;
    .works-video {
      border-radius: 6px;
      left:0;
      top:0;
      height:100%;
      width:100%;
      position:absolute;
    }
  }
  .img-wrapper {
    text-align: center;
    margin: 30px 0;
    .works-img {
      border-radius: 6px;
      width: 90%;
    }
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
