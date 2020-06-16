
<template>
  <div>
    <h1>날씨 알아보기</h1>
    <p>{{ city }}</p>
    <park />
  </div>
</template>

<script>
import park from '@/components/geunsoo.vue'

export default {
  components: {
    park
  },
  data () {
    return {
      city: '서울'
    }
  }
}
</script>
