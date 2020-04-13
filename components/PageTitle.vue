<template>
  <div class="page-title" :class="$mq" :style="computedStyle">
    {{ title }}
  </div>
</template>

<script>
export default {
  name: 'PageTitle',
  props: {
    title: {
      type: String,
      required: true
    },
    backgroundColor: {
      type: String,
      default: '#fff'
    },
    boxShadowColor: {
      type: String,
      default: 'rgba(41 ,41, 41, 0.1)'
    },
    fontColor: {
      type: String,
      default: 'inherit'
    }
  },
  computed: {
    computedStyle () {
      return {
        background: this.backgroundColor,
        boxShadow: `0 0 9px 4px ${this.boxShadowColor}`,
        color: this.fontColor
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .page-title {
    text-align: center;
    font-size: 52px;
    font-weight: bold;
    padding: 26px;
    border-radius: 40px;
    &.xs {
      font-size: 32px;
      padding: 22px;
      border-radius: 26px;
    }
  }
</style>
