<template>
  <div class="works-dismango" :class="$mq">
    <div class="title">
      dis•mango
    </div>
    <div class="sub-title">
      dis•mango is a web-app that can take multiple image files at one time and read its text out loud so you don't have to. Check it out <a href="https://dismango.com/" target="_blank"><b>here</b></a>!
    </div>
    <br/>
    <div class="description">
      Click <a href="https://github.com/dannytan/dismango" target="_blank"><b>here</b></a> to view the source code.
    </div>
    <div class="media-content">
      <img src="../../../assets/img/works/dismango.gif" class="works-gif" />
    </div>
    <div class="description">
      I wrote this app during my last year of undergraduate school, but I wish I wrote it sooner. I can't count the number of times it would have been useful throughout the previous years. The idea came from the fact that for some reason (probably in an effort to help save on textbook costs), professors would photocopy images of actual excerpts of the textbook and give it to us students to read, either physically or digitally. This way every student wouldn't need to have the physical copy of the textbook.
    </div>
    <br/>
    <div class="description">
      Unlike PDFs or Word documents, photocopies are often hard to read and the text isn't searchable. So, with hopes of making my life easier, I decided to spend a weekend creating dis•mango to do the work for me. All you have to do is upload your image file(s), click play, and sit back and relax while the text is read out loud for you.
    </div>
    <br/>
    <div class="description">
      dis•mango is built using <a href="https://vuejs.org/" target="_blank"><b>Vue.js</b></a> and <a href="https://cloud.google.com/vision" target="_blank"><b>Google Vision AI</b></a>. As for the name, I just love mangos!
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
    .works-gif {
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
    .works-gif {
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
    .works-gif {
      width: 100%;
    }
  }
}
</style>
