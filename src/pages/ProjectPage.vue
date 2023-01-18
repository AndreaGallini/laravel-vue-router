<template>
  <div>ProjectPage</div>
  <div v-if="project">
    <h1>{{ project.nome_progetto }}</h1>
  </div>
  <div v-else>
  Wait
</div>

</template>

<script>
import { store } from "../store";
import axios from "axios";
export default {
  name: "ProjectPage",
  data() {
    return {
      store,
      project: null,
    };
  },
  methods: {
    getProject() {
      axios.get(`${this.store.apiURL}/projects/${this.$route.params.slug}`)
        .then((res) => {
        //  console.log(res.data.results);
          if (res.data.success) {
            this.project = res.data.results;
          } else {
            this.$router.push({ name: "NotFound" });
          }
        });
    },
  },
  mounted() {
    this.getProject();
  },
};
</script>

<style lang="scss" scoped></style>
