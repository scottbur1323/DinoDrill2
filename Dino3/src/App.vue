<template>
  <div id="app">
    <app-header/>
      <main>
        <app-job-details/>
        <app-input-form/>
      </main>
    <app-footer/>
  </div>
</template>

<script>
import Header from './components/Header'
import JobDetails from './components/JobDetails'
import InputForm from './components/InputForm'
import Preview from './components/Preview'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    appHeader: Header,
    appJobDetails: JobDetails,
    appInputForm: InputForm,
    appPreview: Preview,
    appFooter: Footer
  }
}
</script>

<style>

htlm {
  margin: 0;
  padding: 0;
}

body {
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}

header {
  grid-row: 1 / 2;
  display: grid;
  grid-template-columns: 25% 50% 15%;
  grid-template-rows: 50% 50%;
  padding-top: 10px;
}

header img {
  grid-row: 1/3;
  grid-column: 1/2;
  height: 100px;
  width: auto;
}

header h1 {
  grid-row: 1/2;
  grid-column: 2/3;
  margin: 0;
  color: #C261CC;
  font-family: serif;
}

main {
  grid-row: 2/3;
  width: 70%;
  margin: 0 auto;
  padding: 10px;
}

main section {
  grid-column: 2/3;
}

small {
  color: black;
  font-size: .5rem;
  margin-left: 10px;
}

a {
  color: #C261CC;
  text-decoration: none;
}

#application-preview {
  border-radius: 6px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
  border: 1px solid darkgrey;
  min-height: 100px;
  margin-top: 20px;
  padding: 10px;
}

footer {
  position: fixed;
  bottom: 0;
  padding: 5px;
}

footer small {
  margin: 0 auto;
}

</style>
