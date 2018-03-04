<template lang="html">
  <div>
    <form id="application-input">
      <label>Apply Here: </label>
      <textarea id="application-text" rows="8" cols="100" v-model="inputForm" ></textarea>
      <input id="submit" type="submit" value="Submit" @click.prevent="appSubmitted" />
    </form>
    <p id="message">{{ submitMessage }}</p>
    <app-preview :inputFormData="inputForm" />
  </div>
</template>

<script>
import Preview from "./Preview"

export default {
  name: "InputForm",
  data: function() {
    return {
      inputForm: "",
      submitMessage: ""
    }
  },
  methods: {
    appSubmitted: function() {
      this.inputForm = ""
      this.submitMessage = "Your application was submitted!"
      setTimeout(() => {
        this.submitMessage = ""
      }, 2000)
    }
  },
  components: {
    appPreview: Preview
  }
}
</script>
