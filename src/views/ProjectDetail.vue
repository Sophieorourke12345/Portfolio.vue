<template>
  <div class="project-detail min-vh-100 container" v-if="project">
    <div class="row align-items-center mb-5">
      <div class="col-md-6 mb-4 mb-md-0" data-aos="fade-right">
        <img :src="project.image" :alt="project.title" class="img-fluid rounded shadow-lg w-100" />
      </div>
      <div class="col-md-6" data-aos="fade-left">
        <h1 class="display-4 font-weight-bold mb-3">{{ project.title }}</h1>
        <p class="lead mb-4">{{ project.description }}</p>
        
        <div class="mb-4">
          <h5 class="font-weight-bold">Technologies</h5>
          <span v-for="(tech, i) in project.technologies" :key="i" class="badge rounded-pill px-3 py-2 mx-1 border border-secondary text-secondary">
            {{ tech }}
          </span>
        </div>
        
        <div class="d-flex mt-4">
          <a v-if="project.github" :href="project.github" target="_blank" class="btn btn-dark text-white me-3 px-4 py-2">
            <i class="fa-brands fa-github mr-2"></i> GitHub Repository
          </a>
          <a v-if="project.live" :href="project.live" target="_blank" class="btn btn-primary px-4 py-2 ml-3">
            <i class="fa-solid fa-arrow-up-right-from-square mr-2"></i> Live Demo
          </a>
        </div>
      </div>
    </div>

    <div v-if="project.demoStatus" class="project-info mb-4">
      <h3 class="font-weight-bold">Demo</h3>
      <p>{{ project.demoStatus }}</p>
    </div>

    <div v-if="project.howToPlay" class="project-info mb-4">
      <h3 class="font-weight-bold">How to Play</h3>
      <ul>
        <li v-for="(step, index) in project.howToPlay" :key="`play-${index}`">{{ step }}</li>
      </ul>
    </div>

    <div v-if="project.rules" class="project-info mb-4">
      <h3 class="font-weight-bold">Rules</h3>
      <ul>
        <li v-for="(rule, index) in project.rules" :key="`rule-${index}`">{{ rule }}</li>
      </ul>
    </div>

    <div v-if="project.scoring" class="project-info mb-4">
      <h3 class="font-weight-bold">Scoring and Outcomes</h3>
      <ul>
        <li v-for="(score, index) in project.scoring" :key="`score-${index}`">{{ score }}</li>
      </ul>
    </div>
  </div>
  <div class="project-detail min-vh-100 container d-flex justify-content-center align-items-center" v-else>
    <h2>Project not found</h2>
  </div>
</template>

<script>
import projectsData from "../data/projects.json";

export default {
  name: "ProjectDetail",
  props: ['id'],
  computed: {
    project() {
      return projectsData.find(p => p.id === this.id);
    }
  },
  mounted() {
    window.scrollTo(0, 0);
  }
};
</script>

<style scoped>
.project-detail {
  padding-top: 120px;
  padding-bottom: 60px;
}
.dark-mode .project-detail {
  color: white;
}
.dark-mode .btn-dark {
  background-color: #333;
  border-color: #333;
}
.project-info {
  border-top: 1px solid #e5e5e5;
  padding-top: 1.5rem;
}
.project-info ul {
  line-height: 1.8;
  font-size: 1.1rem;
}
</style>
