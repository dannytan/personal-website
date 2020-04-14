<template>
  <div class="works">
    <PageTitle
      title="Works"
      background-color="#70D6FF"
      box-shadow-color="rgba(112, 214, 255, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <h1>Coming soon!</h1>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'

export default {
  name: 'Works',
  components: {
    PageTitle
  }
}
</script>

<style lang="scss" scoped>
.works {
  padding: 40px 15% 80px 15%;
  text-align: center;
  h1 {
    margin-top: 30px;
  }
}
</style>
