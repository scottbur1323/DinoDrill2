<template>
  <div>
    <li v-for="(dino, i) in dinoArray" class="profile-card" >
      <header class="profile-header" @click="toggle[i] = !toggle[i]">
        <img :src="dino.image">
        <h2>{{dino.name}}</h2>
      </header>
      <div class="skills-container" v-show="toggle[i]">
        <h4>Skills</h4>
        <ul v-for="skill in dino.skills" class="skills-list">
            <li>{{skill}}</li>
        </ul>
      </div>
    </li>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      dinoArray: [],
      toggle: {
        0: false,
        1: false,
        2: false
      }
    }
  },
  methods: {
    populateTheCard: function() {
      fetch('../static/dinosaurs.json')
      .then(response => {
        return response.json()
      }).then(response => {
        this.dinoArray = response
      }).catch(error => {
        console.log(error)
      })
    }
  },
  mounted: function() {
    this.populateTheCard()
  }
}
</script>
