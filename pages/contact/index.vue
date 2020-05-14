<template>
  <div class="contact">
    <PageTitle
      title="Contact Me"
      background-color="#B032FF"
      box-shadow-color="rgba(176, 50, 255, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <div class="contact-card" :class="$mq">
      <el-row>
        <el-col :xs="24" :md="14">
          <img
            class="contact-card-image"
            src="../../assets/img/contact.png"
            alt="Contact page image" />
        </el-col>
        <el-col :xs="24" :md="10">
          <div class="contact-card-links">
            <div class="email-text">
              <b>Email:</b> dantan808[@]gmail[.]com
            </div>
            <el-row :gutter="computedGutter">
              <el-col :span="12" class="image-container">
                <img
                  style="width: 100%"
                  src="../../assets/img/contact/github.png"
                  alt="GitHub icon"
                  @click="goToGithub"/>
              </el-col>
              <el-col :span="12" class="image-container">
                <img
                  style="width: 100%"
                  src="../../assets/img/contact/linkedin.png"
                  alt="LinkedIn icon"
                  @click="goToLinkedIn"/>
              </el-col>
              <el-col :span="12" class="image-container">
                <img
                  style="width: 100%"
                  src="../../assets/img/contact/instagram.png"
                  alt="Instagram icon"
                  @click="goToInstagram"/>
              </el-col>
              <el-col :span="12" class="image-container">
                <img
                  style="width: 100%"
                  src="../../assets/img/contact/facebook.png"
                  alt="Facebook icon"
                  @click="goToFacebook"/>
              </el-col>
            </el-row>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'

export default {
  name: 'Contact',
  components: {
    PageTitle
  },
  computed: {
    computedGutter () {
      return this.$mq === 'xs' ? 20 : 40
    }
  },
  methods: {
    goToGithub () {
      window.open('https://github.com/dannytan')
    },
    goToLinkedIn () {
      window.open('https://www.linkedin.com/in/dannymtan/')
    },
    goToInstagram () {
      window.open('https://www.instagram.com/_dantan/')
    },
    goToFacebook () {
      window.open('https://www.facebook.com/danny.tan.750')
    }
  }
}
</script>

<style lang="scss" scoped>
.contact {
  padding: 40px 15% 80px 15%;

  .contact-card {
    font-family: 'Roboto Mono', monospace;
    margin: 60px 0;
    box-shadow: 0 0 15px rgba(0,0,0,.15);
    border-radius: 15px;
    width: 100%;
    .contact-card-image {
      height: 100%;
      width: 100%;
    }
    .contact-card-links {
      padding: 20px;
      .email-text {
        text-align: center;
        font-size: 1.2em;
      }
      .image-container {
        padding-top: 30px;
        img {
          cursor: pointer;
        }
      }
    }

    &.md {
      .contact-card-links {
        .email-text {
          font-size: 1em;
        }
      }
    }

    &.sm {
      .contact-card-links {
        padding: 50px;
        .email-text {
          font-size: 1.5em;
        }
      }
    }

    &.xs {
      .contact-card-links {
        padding: 20px;
        .email-text {
          font-size: 0.8em;
        }
        .image-container {
          padding-top: 15px;
        }
      }
    }
  }
}
</style>
