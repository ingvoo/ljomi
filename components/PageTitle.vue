<template>
  <section class="section-intro">
    <div class="container">
      <slot></slot>
    </div>
  </section>
</template>

<style scoped>
.section-intro {
  --fluid-spacing: calc(1rem + 5vw);

  padding-top: calc(var(--fluid-spacing));
  padding-bottom: calc(var(--fluid-spacing) * 2.5);
  background-color: var(--color-base-300);
}
</style>
