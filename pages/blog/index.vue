<template>
  <div class="blog" :class="$mq">
    <PageTitle
      title="Blog"
      background-color="#5DEFA1"
      box-shadow-color="rgba(93, 239, 161, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <div class="page-section">
      <h1 style="text-align: center; margin-top: 20px;">Coming soon!</h1>
      <!--      <div class="blog-text"></div>-->
    </div>
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
    padding: 40px 15% 80px 15%;

    .page-section {
      padding: 30px 10px;
      overflow-y: scroll;
      scrollbar-width: none;
      -ms-overflow-style: none;

      .blog-text {
        font-family: 'Roboto Mono', monospace;
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
      padding: 40px 10% 80px 10%;

      .page-section {
        padding: 20px 10px;

        .blog-text {
          font-size: 17px;
        }
      }
    }

    &.xs {
      padding: 40px 8% 60px 8%;

      .page-section {
        padding: 20px 0;

        .blog-text {
          font-size: 16px;
        }
      }
    }
  }
</style>
