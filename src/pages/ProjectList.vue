<template>

  <div class="row my_container">
    <ProjectCardComponent v-for="project in projects" :obj="project"></ProjectCardComponent>
  </div>
  
</template>

<script>

import ProjectCardComponent from "../components/ProjectCardComponent.vue";
import { store } from "../store";
import axios from "axios";
export default {
  name: "ProjectList",
 components: { ProjectCardComponent },
  data() {
    return {
      store,
      projects: [],
      descriptionLenght: 100,
      
    };
  },
  methods: {
    getProjects() {
      axios.get(`${this.store.apiURL}/projects`).then((res) => {
        this.projects = res.data.results.data;
      });
    },
  },
  mounted() {
    this.getProjects();
  },
};
</script>

<style lang="scss" scoped>
img{
  width: 200px;
}
.my_container{
  padding-top: 2rem;
}
</style>

