<template lang="html">
  <section id="job-details">
    <h2>Job Details</h2>
    <h4>{{ jobTitle }}</h4>
    <p>{{ jobDescription }}</p>
  </section>
</template>

<script>
export default {
  name: "JobDetails",
  data: function() {
    return {
      jobTitle: "",
      jobDescription: ""
    }
  },
  methods: {
    fillDetails: function() {
      fetch('../../static/listing.json')
      .then(response => {
        return response.json()
      })
      .then(data => {
        this.jobTitle = data.title
        this.jobDescription = data.description
      }).catch(error => {
        console.log(error)
      })
    }
  },
  mounted: function() {
    this.fillDetails()
  }
}
</script>
