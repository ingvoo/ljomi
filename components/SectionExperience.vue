<template>
  <section class="section section--large">
    <div class="container">
      <h2 class="section__title">Timeline</h2>
      <article v-for="(work, key) in works" :key="key" class="work">
        <div class="work__info">
          <h3 class="work__title">
            {{ work.title }}
          </h3>
          <p class="work__role">{{ work.role }}</p>
          <!-- <a v-if="work.link" class="work__link" :href="work.link">
            {{ work.link }}
          </a> -->
        </div>
        <time class="block">
          {{ work.start }}
          <span v-if="work.end">- {{ work.end }}</span>
        </time>
        <span class="block">{{ work.location }}</span>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      works: [
        {
          title: 'ZKB',
          location: 'Zürich',
          role: 'UI developer, contractor',
          start: '2023',
          end: null,
        },
        {
          title: 'Die Mobiliar',
          location: 'Bern',
          role: 'UI developer, contractor',
          start: '2020',
          end: '2022',
        },
        {
          title: 'Ljomi GmbH',
          location: 'Bern',
          role: 'Founder',
          start: '2020',
          end: null,
        },
        {
          title: 'Liip AG',
          link: 'https://liip.ch',
          location: 'Bern',
          role: 'Frontend developer',
          start: '2018',
          end: '2020',
        },
        {
          title: 'Ginetta AG',
          link: 'https://ginetta.net',
          location: 'Zürich',
          role: 'Frontend developer',
          start: '2016',
          end: '2018',
        },
        {
          title: 'Freelance',
          location: 'Berlin, Reykjavík',
          role: 'Frontend developer and designer',
          start: '2014',
          end: '2016',
        },
        {
          title: 'Skapalón',
          location: 'Berlin, Reykjavík',
          role: 'Frontend developer',
          start: '2012',
          end: '2014',
        },
        {
          title: 'SAE Institute',
          location: 'Berlin',
          link: 'https://www.sae.edu',
          role: 'Supervisor',
          start: '2012',
          end: '2013',
        },
      ],
    }
  },
}
</script>

<style scoped>
.work {
  display: grid;
  grid-gap: 1rem;
  align-items: baseline;
  padding-top: 1rem;
  padding-bottom: 1rem;
}

.work__title {
  margin-top: 0;
  margin-bottom: 0;
  line-height: 1.4;
}

.work__link {
  font-size: var(--text-sm);
  font-weight: var(--font-bold);
}

.work + .work {
  border-top: 2px solid currentColor;
}

@media only screen and (min-width: 800px) {
  .work {
    grid-template-columns: 1fr 1fr 3fr;
    padding-top: 2rem;
    padding-bottom: 2rem;
  }

  .work__info {
    grid-column-start: 3;
    grid-row-start: 1;
  }

  .work__role {
    margin-top: 0.25rem;
    margin-bottom: 0.25rem;
  }
}
</style>
