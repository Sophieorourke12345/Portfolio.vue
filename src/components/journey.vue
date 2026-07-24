<template>
  <section class="journey-section">
    <Heading
      title="My Journey"
      subtitle="From high performance to human-centred technology"
    />

    <div class="container journey-wrap">
      <div class="journey-intro" data-aos="fade-up">
        <p class="eyebrow">Performance · Learning · Teamwork</p>
        <h2>A journey shaped by ambition, adaptability and continuous growth.</h2>
        <p>
          From representing Ireland in elite sport to studying Psychology and
          Computing and building full-stack applications, every chapter has
          strengthened how I collaborate, solve problems and perform under pressure.
        </p>
      </div>

      <section class="journey-block" aria-labelledby="sport-heading">
        <div class="section-heading">
          <div>
            <p class="eyebrow">High performance</p>
            <h3 id="sport-heading">Sport &amp; international representation</h3>
          </div>
          <p>Competition taught me discipline. Teams taught me how to achieve more together.</p>
        </div>

        <VueSlickCarousel v-bind="sportSettings" class="media-carousel">
          <article v-for="item in sportMoments" :key="item.title" class="sport-slide">
            <div class="sport-image-wrap">
              <img :src="item.image" :alt="item.alt" loading="lazy" />
              <div class="sport-overlay">
                <span>{{ item.label }}</span>
                <h4>{{ item.title }}</h4>
                <p>{{ item.description }}</p>
              </div>
            </div>
          </article>
        </VueSlickCarousel>
      </section>

      <section class="journey-block" aria-labelledby="credentials-heading">
        <div class="section-heading">
          <div>
            <p class="eyebrow">Qualifications &amp; recognition</p>
            <h3 id="credentials-heading">Evidence of continuous learning</h3>
          </div>
          <p>A focused selection of academic and professional credentials.</p>
        </div>

        <VueSlickCarousel v-bind="cardSettings" class="card-carousel">
          <article v-for="credential in credentials" :key="credential.title" class="credential-slide">
            <div class="credential-card">
              <span class="credential-icon" aria-hidden="true">
                <i :class="credential.icon"></i>
              </span>
              <p class="credential-type">{{ credential.type }}</p>
              <h4>{{ credential.title }}</h4>
              <p class="issuer">{{ credential.issuer }}</p>
              <p>{{ credential.description }}</p>
              <a :href="credential.document" target="_blank" rel="noopener noreferrer">
                View credential <i class="fa-solid fa-arrow-up-right-from-square"></i>
              </a>
            </div>
          </article>
        </VueSlickCarousel>
      </section>

      <section class="journey-block references-block" aria-labelledby="references-heading">
        <div class="section-heading">
          <div>
            <p class="eyebrow">Professional references</p>
            <h3 id="references-heading">References available on request</h3>
          </div>
          <p>Contact details and signed letters are kept private and shared directly when required.</p>
        </div>

        <div class="reference-grid">
          <article v-for="reference in references" :key="reference.title" class="reference-card">
            <i :class="reference.icon" aria-hidden="true"></i>
            <div>
              <h4>{{ reference.title }}</h4>
              <p>{{ reference.description }}</p>
            </div>
          </article>
        </div>
      </section>
    </div>
  </section>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import Heading from "./common/heading.vue";

import squashChampion from "../assets/journey/squash-national-championship.jpg";
import squashInternational from "../assets/journey/squash-international.jpg";
import irelandTrailTeam from "../assets/journey/ireland-trail-team.jpg";
import trailRunning from "../assets/journey/trail-running.jpg";

export default {
  components: { VueSlickCarousel, Heading },
  data() {
    return {
      sportSettings: {
        arrows: true,
        dots: true,
        infinite: true,
        autoplay: true,
        autoplaySpeed: 3200,
        speed: 700,
        slidesToShow: 2,
        slidesToScroll: 1,
        pauseOnHover: true,
        responsive: [
          { breakpoint: 900, settings: { slidesToShow: 1, arrows: false } }
        ]
      },
      cardSettings: {
        arrows: true,
        dots: true,
        infinite: true,
        autoplay: true,
        autoplaySpeed: 4600,
        speed: 650,
        slidesToShow: 3,
        slidesToScroll: 1,
        pauseOnHover: true,
        responsive: [
          { breakpoint: 1000, settings: { slidesToShow: 2 } },
          { breakpoint: 700, settings: { slidesToShow: 1, arrows: false } }
        ]
      },
      sportMoments: [
        {
          image: squashChampion,
          label: "Irish Squash",
          title: "National championship",
          description: "Competing at the highest level nationally and celebrating championship success.",
          alt: "Sophie O'Rourke holding an Irish Squash championship trophy"
        },
        {
          image: squashInternational,
          label: "International squash",
          title: "Representing Ireland",
          description: "International competition developed focus, adaptability and confidence under pressure.",
          alt: "Sophie O'Rourke competing in an international squash match"
        },
        {
          image: irelandTrailTeam,
          label: "Team Ireland",
          title: "Trail running team",
          description: "Sharing the challenge with teammates and representing Ireland beyond the squash court.",
          alt: "Sophie O'Rourke with the Irish trail running team"
        },
        {
          image: trailRunning,
          label: "Endurance & adventure",
          title: "Trail running",
          description: "Continuing to pursue ambitious goals through endurance, nature and exploration.",
          alt: "Sophie O'Rourke trail running in the mountains"
        }
      ],
      credentials: [
        {
          type: "Academic recognition",
          title: "Dean's List Award",
          issuer: "Drexel University",
          description: "Recognition of strong academic performance during international university study.",
          document: `${process.env.BASE_URL}credentials/deans-list-award.pdf`,
          icon: "fa-solid fa-graduation-cap"
        },
        {
          type: "Professional qualification",
          title: "Personal Trainer & Nutrition Adviser",
          issuer: "ProFi Fitness School · 2025",
          description: "Comprehensive practical and theoretical training in coaching, movement and nutrition.",
          document: `${process.env.BASE_URL}credentials/personal-trainer-qualification.pdf`,
          icon: "fa-solid fa-dumbbell"
        },
        {
          type: "Specialist certification",
          title: "Functional Biomechanics",
          issuer: "ProFi Fitness School · 87.5%",
          description: "Posture, anatomy and physiology applied to safe, effective movement.",
          document: `${process.env.BASE_URL}credentials/functional-biomechanics.pdf`,
          icon: "fa-solid fa-person-running"
        },
        {
          type: "Specialist certification",
          title: "Fitness Nutrition Adviser",
          issuer: "ProFi Fitness School",
          description: "Evidence-based nutrition principles supporting health and performance.",
          document: `${process.env.BASE_URL}credentials/fitness-nutrition-adviser.pdf`,
          icon: "fa-solid fa-apple-whole"
        }
      ],
      references: [
        {
          title: "Academic",
          description: "Academic performance, research and collaborative university work.",
          icon: "fa-solid fa-book-open"
        },
        {
          title: "Sport & coaching",
          description: "Elite competition, coaching, communication and team contribution.",
          icon: "fa-solid fa-people-group"
        },
        {
          title: "Professional",
          description: "Reliability, initiative and performance in professional environments.",
          icon: "fa-solid fa-briefcase"
        }
      ]
    };
  }
};
</script>

<style scoped lang="scss">
.journey-section {
  padding-bottom: 6rem;
  background: linear-gradient(180deg, #fff 0%, #f6fbf8 45%, #fff 100%);
}

.journey-wrap { max-width: 1240px; }

.journey-intro {
  max-width: 900px;
  margin: 0 auto 5rem;
  text-align: center;
}

.eyebrow {
  margin: 0 0 0.75rem;
  color: #278c62;
  font-size: 0.78rem;
  font-weight: 800;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}

.journey-intro h2 {
  margin-bottom: 1.25rem;
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-weight: 700;
  letter-spacing: -0.045em;
  line-height: 1.05;
}

.journey-intro > p:last-child,
.section-heading > p {
  color: #5c625f;
  font-size: 1.05rem;
  line-height: 1.75;
}

.journey-block { margin-top: 6rem; }

.section-heading {
  display: flex;
  align-items: end;
  justify-content: space-between;
  gap: 2rem;
  margin-bottom: 1.75rem;
}

.section-heading h3 {
  margin: 0;
  font-size: clamp(1.7rem, 3vw, 2.5rem);
  font-weight: 700;
  letter-spacing: -0.035em;
}

.section-heading > p { max-width: 430px; margin: 0; }

.sport-slide,
.credential-slide { padding: 0 0.65rem 1.5rem; }

.sport-image-wrap {
  position: relative;
  height: 470px;
  overflow: hidden;
  border-radius: 28px;
  background: #1b1d1c;
  box-shadow: 0 20px 50px rgba(30, 44, 37, 0.14);
}

.sport-image-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.7s ease;
}

.sport-slide:hover img { transform: scale(1.035); }

.sport-overlay {
  position: absolute;
  inset: auto 0 0;
  padding: 5rem 2rem 1.8rem;
  color: #fff;
  background: linear-gradient(transparent, rgba(10, 15, 12, 0.88));
}

.sport-overlay span {
  font-size: 0.75rem;
  font-weight: 800;
  letter-spacing: 0.13em;
  text-transform: uppercase;
}

.sport-overlay h4 { margin: 0.35rem 0; font-size: 1.7rem; font-weight: 700; }
.sport-overlay p { max-width: 530px; margin: 0; line-height: 1.5; }

.credential-card {
  min-height: 350px;
  padding: 2rem;
  border: 1px solid rgba(39, 140, 98, 0.14);
  border-radius: 24px;
  background: rgba(255, 255, 255, 0.92);
  box-shadow: 0 16px 42px rgba(30, 44, 37, 0.09);
}

.credential-icon {
  display: grid;
  width: 52px;
  height: 52px;
  margin-bottom: 1.5rem;
  border-radius: 16px;
  color: #fff;
  background: #47ba87;
  place-items: center;
}

.credential-type {
  margin-bottom: 0.5rem;
  color: #278c62;
  font-size: 0.72rem;
  font-weight: 800;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}

.credential-card h4 { min-height: 58px; margin-bottom: 0.35rem; font-size: 1.35rem; font-weight: 700; }
.credential-card .issuer { color: #626865; font-weight: 600; }
.credential-card > p:not(.credential-type):not(.issuer) { color: #626865; line-height: 1.6; }
.credential-card a { display: inline-flex; gap: 0.45rem; margin-top: 0.5rem; color: #247d58; font-weight: 700; text-decoration: none; }
.credential-card a:hover { text-decoration: underline; }

.references-block {
  padding: 3rem;
  border-radius: 30px;
  background: #171918;
  color: #fff;
}

.references-block .eyebrow { color: #75d8ac; }
.references-block .section-heading > p { color: #b7bfbb; }

.reference-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; }

.reference-card {
  display: flex;
  gap: 1rem;
  padding: 1.4rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.06);
}

.reference-card > i { margin-top: 0.25rem; color: #75d8ac; font-size: 1.3rem; }
.reference-card h4 { margin-bottom: 0.35rem; font-size: 1.1rem; font-weight: 700; }
.reference-card p { margin: 0; color: #b7bfbb; line-height: 1.55; }

::v-deep .slick-prev:before,
::v-deep .slick-next:before { color: #278c62; font-size: 26px; }
::v-deep .slick-dots li button:before { color: #47ba87; }

@media (max-width: 850px) {
  .section-heading { align-items: start; flex-direction: column; gap: 0.75rem; }
  .sport-image-wrap { height: 430px; }
  .reference-grid { grid-template-columns: 1fr; }
  .references-block { padding: 2rem 1.25rem; }
}

@media (max-width: 520px) {
  .journey-section { padding-bottom: 3rem; }
  .journey-intro { margin-bottom: 3rem; }
  .journey-block { margin-top: 4rem; }
  .sport-slide,
  .credential-slide { padding-inline: 0.25rem; }
  .sport-image-wrap { height: 440px; border-radius: 22px; }
  .sport-overlay { padding: 4rem 1.35rem 1.35rem; }
  .sport-overlay h4 { font-size: 1.45rem; }
  .credential-card { min-height: 325px; padding: 1.5rem; }
}

@media (prefers-reduced-motion: reduce) {
  .sport-image-wrap img { transition: none; }
}
</style>
