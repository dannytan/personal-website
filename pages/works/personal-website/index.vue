<template>
  <div class="works-personal-website" :class="$mq">
    <div class="title">
      Personal Website
    </div>
    <div class="sub-title">
      This website was built as a way to display some of my work as both a developer and musician in hopes of finding people to connect with, like yourself!
    </div>
    <div class="description">
      For this project, I used <a href="https://nuxtjs.org/" target="_blank"><b>Nuxt</b></a>, a progressive framework based on Vue.js. For more information and detailed explanation on how things work, check out the <a href="https://nuxtjs.org/guide" target="_blank"><b>Nuxt.js docs</b></a>.
    </div>
    <div class="description">
      The site is being hosted on AWS using <a href="https://aws.amazon.com/s3/" target="_blank"><b>S3 (Simple Storage Service)</b></a> and <a href="https://aws.amazon.com/cloudfront/" target="_blank"><b>CloudFront (CDN)</b></a>. I'm also using <a href="https://jenkins.io/" target="_blank"><b>Jenkins</b></a> for automated builds and deployments.
    </div>
  </div>
</template>

<script>
export default {
  name: 'PersonalWebsite'
}
</script>

<style lang="scss" scoped>
.works-personal-website {
  font-family: 'Roboto Mono', monospace;
  padding: 8% 15% 80px 15%;
  .title {
    font-size: 52px;
    font-weight: bold;
  }
  .sub-title {
    font-size: 22px;
    line-height: 1.3;
    margin: 20px 0;
  }
  .description {
    font-size: 18px;
    line-height: 1.3;
    margin: 14px 0;
  }
  a {
    color: inherit;
    text-decoration: none;
  }
  &.md {
    padding: 8% 10% 80px 10%;
  }
  &.sm {
    padding: 8% 8% 80px 8%;
  }
  &.xs {
    padding: 8% 5% 80px 5%;
    .title {
      font-size: 30px;
    }
    .sub-title {
      font-size: 18px;
    }
    .description {
      font-size: 16px;
    }
  }
}
</style>
