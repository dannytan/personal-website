<template>
  <div class="resources" :class="$mq">
    <PageTitle
      v-scroll-reveal="{origin: 'top', distance: '50px', delay: 200}"
      title="Resources"
      background-color="#5DEFA1"
      box-shadow-color="rgba(93, 239, 161, 0.4)"
      font-color="#fff"
    ></PageTitle>
    <div class="page-section">
      <div v-scroll-reveal="{distance: '10px', delay: 200}" class="resources-text">
        Here are some online resources that I either reference on a daily basis or have helped me on my journey (both technical and non-technical) so far.  I am always seeking to learn more about technology, music, personal finance, and everything in between. So, if you have a recommendation for something that has helped you in the past, please feel free to share!
      </div>
      <div
        v-for="(resource, index) in resources"
        :key="index"
        v-scroll-reveal="{distance: '10px', delay: 200}"
        class="resource-card"
        @click="goToResource(resource.link)">
        <div class="resource-card-tag" :style="setColor(resource.tagColor)">
          {{ resource.category }}
        </div>
        <div class="resource-card-content link">
          {{ resource.title }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle'

export default {
  name: 'Resources',
  components: {
    PageTitle
  },
  data () {
    return {
      resources: [{
        title: 'Ultimate AWS Certified Developer Associate 2020',
        link: 'https://www.udemy.com/course/aws-certified-developer-associate-dva-c01/',
        category: 'Career Development',
        tagColor: '#FF5F6D'
      }, {
        title: 'How I manage my personal finances as a minimalist.',
        link: 'https://www.youtube.com/watch?v=YyaVya4YSwU',
        category: 'Finances',
        tagColor: '#065ED4'
      }, {
        title: 'What Will You Say When You Don\'t Know?',
        link: 'https://open.spotify.com/episode/6bkqqtvW8rZ8IQcIx8EyPC?si=FsfHsOprQReEKnuwlNeGNA',
        category: 'Career Development',
        tagColor: '#FF5F6D'
      }, {
        title: 'How Do I Communicate with Non-Technical Decision Makers?',
        link: 'https://open.spotify.com/episode/0LJijvgFFhWy0KzS9f1RFq?si=POC9sItOSYCJ9g1MUNCkyA',
        category: 'Career Development',
        tagColor: '#FF5F6D'
      }, {
        title: 'GapClick',
        link: 'https://gapclick.app/',
        category: 'Drums',
        tagColor: '#DC7C01'
      }, {
        title: 'How Questions Influence Pathways to Solutions',
        link: 'https://open.spotify.com/episode/5AZvgM7LbNRXqALz8SosEN?si=jcdKnEV_QI-e1mc_LULGjA',
        category: 'Career Development',
        tagColor: '#FF5F6D'
      }, {
        title: 'Morning Brew',
        link: 'https://www.morningbrew.com/',
        category: 'News',
        tagColor: '#01A467'
      }, {
        title: 'iOS 13 & Swift 5 - The Complete iOS App Development Bootcamp',
        link: 'https://www.udemy.com/course/ios-13-app-development-bootcamp/',
        category: 'Career Development',
        tagColor: '#FF5F6D'
      }, {
        title: 'InvestTalk',
        link: 'https://open.spotify.com/show/6RlP2Dft6sX6sPv2YBbZKD?si=a-rsq4eqQoe6qsZEcncBxA',
        category: 'Finances',
        tagColor: '#065ED4'
      }, {
        title: 'These four “clean code” tips will dramatically improve your engineering team’s productivity',
        link: 'https://engineering.videoblocks.com/these-four-clean-code-tips-will-dramatically-improve-your-engineering-teams-productivity-b5bd121dd150',
        category: 'Career Development',
        tagColor: '#FF5F6D'
      }, {
        title: '7 Skills of Highly “Effective” Programmers',
        link: 'https://medium.com/better-programming/7-habits-of-highly-effective-programmers-563ee3b63f33',
        category: 'Career Development',
        tagColor: '#FF5F6D'
      }, {
        title: 'FPU - Financial Peace University',
        link: 'https://www.daveramsey.com/fpu',
        category: 'Finances',
        tagColor: '#065ED4'
      }, {
        title: 'The Dave Ramsey Show',
        link: 'https://open.spotify.com/show/5exfRPDNCBHmntEkJrlLmX?si=qwAyZmjIRe2dh6LJ8TCrmw',
        category: 'Finances',
        tagColor: '#065ED4'
      }]
    }
  },
  methods: {
    goToResource (link) {
      window.open(link)
    },
    setColor (color) {
      return {
        backgroundColor: color
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .resources {
    padding: 40px 15% 80px 15%;

    .page-section {
      padding: 30px 10px;
      overflow-y: scroll;
      scrollbar-width: none;
      -ms-overflow-style: none;

      .link {
        color: inherit;
      }

      .resources-text {
        font-family: 'Roboto Mono', monospace;
        font-size: 18px;
        line-height: 1.8;
        hyphens: auto;
        margin-bottom: 30px;
      }

      .resource-card {
        font-family: 'Roboto Mono', monospace;
        font-size: 14px;
        margin: 15px 0;
        padding: 15px 20px;
        box-shadow: 0 0 9px 4px rgba(41 ,41, 41, 0.1);
        border-radius: 10px;
        cursor: pointer;
        &:hover {
          background-color: #FAFAFA;
        }
        .resource-card-tag {
          display: inline-block;
          color: #fff;
          font-weight: bold;
          padding: 4px 8px;
          border-radius: 5px;
        }
        .resource-card-content {
          display: inline;
          font-weight: bold;
          text-decoration: none;
          line-height: 1.7em;
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

        .resources-text {
          font-size: 16px;
        }
      }
    }

    &.xs {
      padding: 40px 8% 60px 8%;

      .page-section {
        padding: 20px 10px;

        .resources-text {
          font-size: 13px;
        }

        .resource-card {
          font-size: 12px;
          .resource-card-tag {
            display: table;
          }
          .resource-card-content {
            display: table;
            margin-top: 10px;
          }
        }
      }
    }
  }
</style>
