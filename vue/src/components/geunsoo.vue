<template lang="html">
  <div>
    <p>{{ name }}</p>
    <button type="button" name="button" @click="changeClick">change</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'parkgeunsoo'
    }
  },
  methods: {
    changeClick() {
      this.name = '~ parkgeunsoo ~';
    }
  }
}
</script>

<style lang="css" scoped>
</style>
