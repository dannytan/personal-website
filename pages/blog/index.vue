<template>
  <div class="blog">
    <PageTitle
      title="Blog"
      background-color="#5DEFA1"
      box-shadow-color="rgba(93, 239, 161, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <h1>Coming soon!</h1>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'

export default {
  name: 'Blog',
  components: {
    PageTitle
  }
}
</script>

<style lang="scss" scoped>
.blog {
  margin: 40px 15% 80px 15%;
  text-align: center;
  h1 {
    margin-top: 30px;
  }
}
</style>
