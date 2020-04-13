<template>
  <div class="about" :class="$mq">
    <PageTitle title="About Dan"></PageTitle>
    <div class="page-section">
      <div class="about-text">
        Daniel is a <b>full-stack software developer</b> based out of <b>Honolulu, HI</b> with a strong foundation in engineering principles across multiple platforms and technologies.  He has a passion for writing, testing, debugging code, and designing user interfaces. Daniel is self-driven and able to quickly learn and master new technologies, while being successful in both team and independent environments.<br/>
        In 2018, Daniel graduated magna cum laude with a <b>B.S. in Computer Science</b> from the <b>University of Hawaiʻi at Mānoa</b>.  He currently works as a software engineer for <a class="link" href="https://www.datahouse.com" target="_blank"><b>DataHouse</b></a>, building enterprise-level applications using mostly <b>#Node.js</b>, <b>#JavaScript</b>, <b>#Vue.js</b>, <b>#SQL</b>, <b>#Jenkins</b>, and <b>#AWS</b>. A recently certified <b>AWS Certified Cloud Practitioner</b>, Daniel is also working toward becoming an <b>AWS Certified Developer Associate</b> in the near future.<br/>
        Aside from writing code, Daniel has a passion for music and has been drumming for around 15 years. He serves as a drummer at <a class="link" href="https://c4.church" target="_blank"><b>C4 Church</b></a> and also gigs with local artists and musicians from time to time. When he’s not behind a keyboard or drum set, you can find Daniel out in the water surfing or playing with his dog, Maya.
      </div>
      <img src="../../assets/img/bio-1.jpg" alt="bio" class="bio-image-1"/>
      <img src="../../assets/img/bio-2.jpg" alt="bio" class="bio-image-2"/>
    </div>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'

export default {
  name: 'About',
  components: {
    PageTitle
  }
}
</script>

<style lang="scss" scoped>
.about {
  margin: 40px 15% 80px 15%;
  .page-section {
    padding: 30px 10px;
    overflow-y: scroll;
    overflow: -moz-scrollbars-none;
    -ms-overflow-style: none;
    .bio-image-1 {
      margin-top: 40px;
      width: 32.33333%;
      border-radius: 20px;
      float: left;
    }
    .bio-image-2 {
      margin-top:40px;
      width: 64.66666%;
      border-radius: 20px;
      float: right;
    }
    .about-text {
      font-size: 18px;
      line-height: 1.8;
      white-space: pre-line;
      .link {
        color: inherit;
      }
    }
  }
  .page-section::-webkit-scrollbar {
    display: none;
  }
  &.sm {
    margin: 40px 10% 80px 10%;
    .page-section {
      padding: 20px 10px;
      .about-text {
        font-size: 17px;
      }
    }
  }
  &.xs {
    margin: 40px 8% 60px 8%;
    .page-section {
      padding: 20px 0;
      .bio-image-1 {
        margin-top: 30px;
        width: 100%;
        border-radius: 15px;
      }
      .bio-image-2 {
        margin-top: 30px;
        width: 100%;
        border-radius: 15px;
      }
      .about-text {
        font-size: 16px;
      }
    }
  }
}
</style>
