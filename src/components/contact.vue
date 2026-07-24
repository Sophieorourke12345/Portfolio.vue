<template>
  <div>
    <footer class="mt-5 text-lg-start" id="contact">
      <hr class="my-4"/>
        <section class="row">
            <div class="col-md-3 col-lg-3 col-xl-3 mx-auto mt-3">
              <h6 class="text-uppercase mb-4 font-weight-bold">Contact Details</h6>
              <p>
                <i class="fab fa-linkedin"></i> LinkedIn profile coming soon
              </p>
              <p>
                <a href="https://github.com/Sophieorourke12345" target="_blank">
                  <i class="fab fa-github"></i> GitHub
                </a>
              </p>
              <p>
                <a href="mailto:sophorourke2000@gmail.com">
                  <i class="fas fa-envelope"></i> sophorourke2000@gmail.com
                </a>
              </p>
              <p>
                <a href="tel:+353851693867">
                  <i class="fas fa-phone"></i> 085 169 3867
                </a>
              </p>
              <p>
                <i class="fas fa-map-marker-alt"></i> Cork, Ireland
              </p>
            </div>

            <div class="col-md-2 col-lg-2 col-xl-2 mx-auto mt-3">
              <h6 class="text-uppercase mb-4 font-weight-bold">Focus Areas</h6>
              <p>Web Development</p>
              <p>UX Design</p>
              <p>Human-Centred Computing</p>
            </div>

            <div class="col-md-4 col-lg-3 col-xl-3 mx-auto mt-3">
              <h6 class="text-uppercase mb-4 font-weight-bold">Links</h6>
              <p class="scroll-to" @click="scrollToSection('summary')">Summary</p>
              <p class="scroll-to" @click="scrollToSection('about')">About</p>
              <p class="scroll-to" @click="scrollToSection('practicle_skills')">Skills</p>
              <p class="scroll-to" @click="scrollToSection('projects')">Projects</p>
              <p><a href="https://sophieorourke12345.github.io/Portfolio.vue/">Portfolio website</a></p>
            </div>

            <div class="col-md-3 col-lg-2 col-xl-2 mx-auto mt-3">
              <h6 class="text-uppercase mb-4 font-weight-bold">Follow Me</h6>
              <a class="btn btn-floating m-1" href="https://github.com/Sophieorourke12345" role="button">
                <i class="fab fa-github"></i>
              </a>
              <a class="btn btn-floating m-1" href="mailto:sophorourke2000@gmail.com" role="button">
                <i class="fas fa-envelope"></i>
              </a>
            </div>
        </section>
      <hr/>
      <div class="text-center p-3">
        © 2026 Sophie O'Rourke | Built with
        <a href="https://vuejs.org/">Vue.js</a>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "FooterComponent",
  methods: {
     scrollToSection(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
};
</script>

<style scoped>
.scroll-to {
  cursor: pointer;
}
footer {
  section.row p a {
    color: black;
  }
}
</style>
