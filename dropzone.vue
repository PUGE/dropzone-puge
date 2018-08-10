<template>
  <div class="dropzone" @click="checkFile" @drop="onDrag" @dragleave="stop" @ragover="stop" @dragenter="stop" @dragover="stop">
    <input type="file" :accept="accept" @change="$emit('getFile', $event)"/>
    <slot class="slot"></slot>
  </div>
</template>

<script>
export default {
  props: {
    accept: String
  },
  methods: {
    stop (e) {
      e.preventDefault()
    },
    onDrag (e) {
      e.preventDefault()
      this.$emit('getFile', e)
    },
    checkFile () {
      this.$el.childNodes[0].click()
    }
  }
}
</script>

<style scoped>
  .dropzone {
    position: relative;
    height: 200px;
    background-color: blue;
  }
  input {
    position: absolute;
    width: 0;
    height: 0;
    opacity: 0;
  }
  .slot {
    pointer-events: none;
  }
</style>
