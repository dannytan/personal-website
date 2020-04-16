<template>
  <div class="works" :class="$mq">
    <PageTitle
      title="Works"
      background-color="#70D6FF"
      box-shadow-color="rgba(112, 214, 255, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <el-row gutter="40" style="margin-top: 60px;">
      <el-col :xs="24" :sm="12">
        <nuxt-link to="/works/personal-website">
          <ImageCard
            class="works-card"
            title="This Website"
            background-image-path="works/personal-website.png"
            @click="cardClicked('personal-website')"
          ></ImageCard>
        </nuxt-link>
      </el-col>
      <el-col :xs="24" :sm="12">
        <nuxt-link to="/works/dismango">
          <ImageCard
            class="works-card"
            title="dis•mango"
            background-image-path="works/dismango.png"
            @click="cardClicked('dismango')"
          ></ImageCard>
        </nuxt-link>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'
import ImageCard from '~/components/ImageCard'

export default {
  name: 'Works',
  components: {
    PageTitle,
    ImageCard
  },
  methods: {
    cardClicked (card) {
      console.log(`${card} card was clicked`)
    }
  }
}
</script>

<style lang="scss" scoped>
.works {
  padding: 40px 15% 80px 15%;
  .works-card {
    margin: 12px 0;
  }
  &.md {
    padding: 40px 8% 80px 8%;
  }
  &.sm {
    padding: 40px 5% 80px 5%;
  }
  &.xs {
    padding: 40px 5% 80px 5%;
  }
}
</style>
