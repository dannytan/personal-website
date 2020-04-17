<template>
  <div
    class="image-card"
    :style="{ backgroundImage: `url(${ computedBackgroundImage })` }"
    @click="onClick">
    <div class="overlay"></div>
    <div class="card-title">
      {{ title }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'ImageCard',
  props: {
    title: {
      type: String,
      required: true
    },
    backgroundImagePath: {
      type: String,
      required: true
    }
  },
  computed: {
    computedBackgroundImage () {
      return require(`../assets/img/${this.backgroundImagePath}`)
    }
  },
  methods: {
    onClick () {
      this.$emit('click')
    }
  }
}
</script>

<style lang="scss" scoped>
  .image-card {
    position: relative;
    color: #fff;
    height: 300px;
    background-size: cover;
    background-position: center;
    background-color: #47494e;
    box-shadow: 0 0 9px 4px rgba(41 ,41, 41, 0.1);
    border-radius: 10px;
    cursor: pointer;
    .overlay {
      border-radius: 10px;
      background: linear-gradient(180deg, transparent 62%, rgba(0,0,0,0.00345888) 63.94%, rgba(0,0,0,0.014204) 65.89%, rgba(0,0,0,0.0326639) 67.83%, rgba(0,0,0,0.0589645) 69.78%, rgba(0,0,0,0.0927099) 71.72%, rgba(0,0,0,0.132754) 73.67%, rgba(0,0,0,0.177076) 75.61%, rgba(0,0,0,0.222924) 77.56%, rgba(0,0,0,0.267246) 79.5%, rgba(0,0,0,0.30729) 81.44%, rgba(0,0,0,0.341035) 83.39%, rgba(0,0,0,0.367336) 85.33%, rgba(0,0,0,0.385796) 87.28%, rgba(0,0,0,0.396541) 89.22%, rgba(0,0,0,0.4) 91.17%);
      height: 100%;
      width: 100%;
      visibility: hidden;
      opacity: 0;
      transition: visibility 0s, opacity 350ms linear;
    }
    .card-title {
      font-family: 'Roboto Mono', monospace;
      position: absolute;
      left: 25px;
      bottom: 15px;
      font-size: 18px;
      font-weight: bold;
      visibility: hidden;
      opacity: 0;
      transition: visibility 0s, opacity 350ms linear;
    }

    &:hover {
      .overlay,
      .card-title {
        visibility: visible;
        opacity: 1;
      }
    }
  }
</style>
