<template>
  <header>
    <div class="container container--large">
      <div class="site-header__layout">
        <ljomi-logo />
        <nav>
          <a class="link" data-analytics="Resume" href="/cv_ingvi-jonasson.pdf">
            My Resume
          </a>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
import LjomiLogo from '@/components/LjomiLogo.vue'

export default {
  components: {
    LjomiLogo,
  },
}
</script>

<style scoped>
header {
  padding-top: clamp(1rem, 1.5rem + 1.5vw, 3rem);
  padding-bottom: clamp(1rem, 1.5rem + 1.5vw, 3rem);
  background-color: var(--color-base-300);
}

.site-header__layout {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav a {
  text-decoration: none;
  font-weight: var(--font-bold);
}
</style>
