<template>
  <div class="page-title" :class="$mq">
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
    }
  }
}
</script>

<style lang="scss" scoped>
  .page-title {
    text-align: center;
    font-size: 52px;
    font-weight: bold;
    background: #FF5475;
    color: #fff;
    padding: 26px;
    border-radius: 40px;
    box-shadow: 0 0 9px 4px rgba(255, 84, 117, 0.4);
    &.xs {
      font-size: 32px;
      padding: 22px;
      border-radius: 26px;
    }
  }
</style>
