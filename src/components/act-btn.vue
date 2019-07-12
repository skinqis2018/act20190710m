<template>
  <div @click="openMask" class="btn">{{text}}</div>
</template>
<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
      default: ''
    }
  },
  methods: {
    openMask () {
      eventBus.$emit('openMask')
    }
  }
}
</script>
