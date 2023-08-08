<script setup>
import { reactive } from "vue";

/* Array to contain our job data */
const jobs = reactive([]);
</script>

<template>
  <!-- container for the entire page -->
  <div class="container">
    <!-- a div to layout all the jobs in our database -->
    <div class="jobs">
      <h1>JOBS</h1>
      <div class="job" v-for="job in jobs" :key="job.jobUrl">
        <div class="header">
          <h2>{{ job.title }}</h2>
          <span class="material-icons"> delete </span>
        </div>
        <h4>{{ job.jobUrl }}</h4>
        <p>{{ job.desc }}</p>
        <h3>{{ job.location }}</h3>
        <h3>{{ job.contact }}</h3>
        <h3>{{ job.expires }}</h3>
        <span>posted on {{ job.createdOn}}</span>
      </div>
    </div>
    <!-- a div to layout our form sidebar -->
    <div class="side">
    </div>
  </div>
</template>

<style scoped>
/* These two classes are to layout the title and the delete button on a job */
.header {
  display: flex;
  justify-content: space-between;
}
.header span {
  padding: 15px;
  font-size: 2em;
  cursor: pointer;
}
</style>
