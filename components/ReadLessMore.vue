<template>
  <div>
    <div class="text-sm">
      <span class="opacity-80 inline" v-html="trimText"></span>
      <span class="cursor-pointer inline hover:underline" @click="isLess = !isLess" v-if="text.length != 0 && text.length > trimText.length">... Read More</span>
      <span class="cursor-pointer inline hover:underline" @click="isLess = !isLess" v-else :class="text.length == 0 ? 'hidden' : ''"> Read Less </span>
    </div>

  </div>
</template>

<script>
  export default {
    props: ['text'],
    data() {
      return {
        isLess: true,
      }
    },
    computed: {
      trimText () {
        return this.text.substring(0, this.count)
      },
      count () {
        return this.isLess ? 90 : 400
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
