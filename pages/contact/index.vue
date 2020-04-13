<template>
  <div class="contact">
    <PageTitle
      title="Contact Me"
      background-color="#B032FF"
      box-shadow-color="rgba(176, 50, 255, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <h1>Coming soon!</h1>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'

export default {
  name: 'Contact',
  components: {
    PageTitle
  }
}
</script>

<style lang="scss" scoped>
.contact {
  margin: 40px 15% 80px 15%;
  text-align: center;
  h1 {
    margin-top: 30px;
  }
}
</style>
