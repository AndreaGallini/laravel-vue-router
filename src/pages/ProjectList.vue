<template>
  <h1>ProjectList</h1>
  <div class="row">
    <div class="col-3 col-md-4" v-for="project in projects">
      <h6>{{ project.nome_progetto }}</h6>
      <p>{{ project.descrizione }}</p>
      <p>{{ project.slug }}</p>
      <img :src="`${store.imagePath}${project.img}`" class="card-img-top" >
      <router-link
        :to="{ name: 'ProjectPage', params: { slug: project.slug } }"
        class="btn btn-primary"
        >Visualizza il dettaglio del progetto</router-link
      >
    </div>
  </div>
  <div class="row">
  <ProjectCard v-for="project in projects" :obj="project"></ProjectCard>
  </div>
</template>

<script>
import ProjectCard from '../components/ProjectCard.vue';
import { store } from "../store";
import axios from "axios";
export default {
  name: "ProjectList",
  
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
}</style>
