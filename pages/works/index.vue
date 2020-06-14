<template>
  <div class="works" :class="$mq">
    <PageTitle
      v-scroll-reveal="{origin: 'top', distance: '50px', delay: 200}"
      title="Works"
      background-color="#70D6FF"
      box-shadow-color="rgba(112, 214, 255, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <el-row gutter="40" style="margin-top: 60px;">
      <el-col :xs="24" :sm="12">
        <nuxt-link to="/works/personal-website">
          <ImageCard
            v-scroll-reveal="{distance: '10px', delay: 200}"
            class="works-card"
            title="This Website"
            background-image-path="works/personal-website.png"
            @click="cardClicked('personal-website')"
          ></ImageCard>
        </nuxt-link>
      </el-col>
      <el-col :xs="24" :sm="12">
        <ImageCard
          v-scroll-reveal="{distance: '10px', delay: 200}"
          class="works-card"
          title="@dantandrums"
          background-image-path="works/dantandrums.png"
          @click="dantandrumsClicked"
        ></ImageCard>
      </el-col>
      <el-col :xs="24" :sm="12">
        <nuxt-link to="/works/dismango">
          <ImageCard
            v-scroll-reveal="{distance: '10px', delay: 200}"
            class="works-card"
            title="dis•mango"
            background-image-path="works/dismango.png"
            @click="cardClicked('dismango')"
          ></ImageCard>
        </nuxt-link>
      </el-col>
      <el-col :xs="24" :sm="12">
        <nuxt-link to="/works/hacc">
          <ImageCard
            v-scroll-reveal="{distance: '10px', delay: 200}"
            class="works-card"
            title="HACC 2017"
            background-image-path="works/hacc.png"
            @click="cardClicked('hacc')"
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
    },
    dantandrumsClicked () {
      window.open('https://www.instagram.com/dantandrums/')
    }
  }
}
</script>

<style lang="scss" scoped>
.works {
  padding: 40px 15% 120px 15%;
  .works-card {
    margin: 20px 0;
  }
  &.md {
    padding: 40px 8% 120px 8%;
  }
  &.sm {
    padding: 40px 5% 120px 5%;
  }
  &.xs {
    padding: 40px 5% 100px 5%;
    .works-card {
      margin: 12px 0;
    }
  }
}
</style>
