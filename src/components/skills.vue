<template>
  <section id="practicle_skills">
    <Heading :title="'Practical Skills'" :subtitle="'Explore My'" />
    <div class="container">
      <div class="d-flex justify-content-center flex-wrap">
        <article
          class="position-relative"
          v-for="(skill, index) in skills"
          :key="index"
          data-aos="zoom-in" :data-aos-duration="getAosDuration(index)"
          @mouseover="toggleSkillLevel(index, true)"
          @mouseout="toggleSkillLevel(index, false)"
        >
          <h3>
            <img 
              v-if="skill.imageSrc"
              :src="`${publicPath}icons/${skill.imageSrc}`" 
              class="skill-image mr-3"
            />

            {{ skill.name }}
          </h3>
        </article>
      </div>
     
    </div>
  </section>
</template>

<script>
import Heading from "./common/heading.vue";
export default {
  components: {
    Heading,
  },
  data() {
    return {
      publicPath: process.env.BASE_URL,
      skills: [
        { name: 'Python', imageSrc: 'python.png' },
        { name: 'JavaScript', imageSrc: 'js.png' },
        { name: 'HTML', imageSrc: 'html.png' },
        { name: 'CSS', imageSrc: 'css.png' },
        { name: 'SQL', imageSrc: 'sql.svg' },
        { name: 'C#', imageSrc: 'csharp.svg' },
        { name: 'Unity', imageSrc: 'unity.svg' },
        { name: 'Git', imageSrc: 'git.png' },
        { name: 'GitHub', imageSrc: 'github.png' },
        { name: 'Vue.js', imageSrc: 'vue.png' },
        { name: 'Zapier', imageSrc: 'zapier.svg' },
        { name: 'Less Annoying CRM', imageSrc: 'crm.svg' },
        { name: 'SPSS Statistics', imageSrc: 'spss.svg' },
        { name: 'Data Analysis', imageSrc: 'data-analysis.svg' },
        { name: 'Miro', imageSrc: 'miro.svg' },
        { name: 'Figma', imageSrc: 'figma.svg' },
        { name: 'UX Design', imageSrc: 'ux.svg' },
        { name: 'Excel', imageSrc: 'excel.svg' },
      ],
    };
  },
  methods: {
    toggleSkillLevel(index) {
      this.$set(this.skills, index, { ...this.skills[index], showLevel: !this.skills[index].showLevel });
    },
    getAosDuration(index) {
      return index * 400;
    },
  },
};
</script>

<style scoped>

article {
  width: 15rem;
  height: 5rem;
  gap: 0.5rem;

}
.skill-image{
  height:30px;
  width:30px;
}
</style>
