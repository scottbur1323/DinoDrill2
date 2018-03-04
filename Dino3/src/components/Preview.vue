<template lang="html">
  <div>
    <button id="preview-toggle" @click.prevent="toggleIt">Show Preview</button>
    <section id="application-preview" v-show="toggle">{{ inputFormData }}</section>
  </div>
</template>

<script>
export default {
  name: "Preview",
  props: ['inputFormData'],
  data: function() {
    return {
      toggle: false
    }
  },
  methods: {
    toggleIt: function() {
      this.toggle = !this.toggle
    }
  }
}
</script>
