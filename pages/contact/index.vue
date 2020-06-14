<template>
  <div class="contact">
    <PageTitle
      v-scroll-reveal="{origin: 'top', distance: '50px', delay: 200}"
      title="Contact Me"
      background-color="#B032FF"
      box-shadow-color="rgba(176, 50, 255, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <div v-scroll-reveal="{distance: '10px', delay: 200}" class="contact-card" :class="$mq">
      <el-row>
        <el-col :xs="24" :md="14">
          <img
            class="contact-card-image"
            src="../../assets/img/contact.png"
            alt="Contact page image" />
        </el-col>
        <el-col :xs="24" :md="10">
          <div class="contact-card-links">
            <el-row :gutter="computedGutter">
              <el-col :span="12" class="image-container">
                <img
                  class="enlarge-on-hover"
                  style="width: 100%"
                  src="../../assets/img/contact/github.png"
                  alt="GitHub icon"
                  @click="goToGithub"/>
              </el-col>
              <el-col :span="12" class="image-container">
                <img
                  class="enlarge-on-hover"
                  style="width: 100%"
                  src="../../assets/img/contact/linkedin.png"
                  alt="LinkedIn icon"
                  @click="goToLinkedIn"/>
              </el-col>
              <el-col :span="12" class="image-container">
                <img
                  class="enlarge-on-hover"
                  style="width: 100%"
                  src="../../assets/img/contact/instagram.png"
                  alt="Instagram icon"
                  @click="goToInstagram"/>
              </el-col>
              <el-col :span="12" class="image-container">
                <img
                  class="enlarge-on-hover"
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
    <el-form ref="form" v-scroll-reveal="{distance: '10px', delay: 500}" :model="form" :rules="rules" class="contact-form">
      <el-row :gutter="20">
        <el-col :xs="24" :sm="12">
          <el-form-item label="Name" prop="name">
            <el-input v-model="form.name"></el-input>
          </el-form-item>
        </el-col>
        <el-col :xs="24" :sm="12">
          <el-form-item label="Email" prop="email">
            <el-input v-model="form.email"></el-input>
          </el-form-item>
        </el-col>
      </el-row>
      <el-form-item label="Message" prop="message">
        <el-input type="textarea" :autosize="{ minRows: 4 }" v-model="form.message"></el-input>
      </el-form-item>
      <el-form-item style="text-align: right">
        <el-button class="send-button enlarge-on-hover" :loading="messageSending" @click="submitForm('form')">
          Send
        </el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'

export default {
  name: 'Contact',
  components: {
    PageTitle
  },
  data () {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      },
      rules: {
        name: [
          { required: true, message: 'Please input your name', trigger: 'blur' }
        ],
        email: [
          { required: true, message: 'Please input your email address', trigger: 'blur' }
        ],
        message: [
          { required: true, message: 'Message cannot be blank', trigger: 'blur' }
        ]
      },
      messageSending: false
    }
  },
  computed: {
    computedGutter () {
      return this.$mq === 'xs' ? 20 : 40
    }
  },
  methods: {
    formMessageBody () {
      return {
        name: this.form.name,
        email: this.form.email,
        message: this.form.message
      }
    },
    submitForm (formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          this.messageSending = true
          this.$axios.$post('https://nnxvv3dmp6.execute-api.us-west-2.amazonaws.com/dev/contact', this.formMessageBody())
            .then((response) => {
              this.$notify.success({
                title: 'Success',
                message: response.message
              })
            })
            .catch((err) => {
              this.$notify.error({
                title: 'Error',
                message: err.message
              })
            })
            .finally(() => {
              this.messageSending = false
            })
        }
      })
    },
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
    margin: 40px 0;
    box-shadow: 0 0 15px rgba(0,0,0,.15);
    border-radius: 15px;
    width: 100%;
    .contact-card-image {
      height: 100%;
      width: 100%;
    }
    .contact-card-links {
      padding: 20px;
      .image-container {
        padding-top: 16px;
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
  .contact-form {
    font-family: 'Roboto Mono', monospace;
    .send-button {
      background-color: #B032FF;
      color: #fff;
      border: none;
      font-weight: bold;
    }
  }
}
</style>
