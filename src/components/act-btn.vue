<template>
  <div>
    <div 
      v-if="disabled" 
      class="btn"
      :class="{disabled : disabled}">{{text}}</div>
    <div v-else @click="openMask" class="btn">{{text}}</div>
  </div>
</template>
<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
      default: ''
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    openMask () {
      eventBus.$emit('openMask')
    }
  }
}
</script>
