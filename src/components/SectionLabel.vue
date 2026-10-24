<script setup>
  defineProps({
    number: {
      type: String,
      required: true
    },

    title: {
      type: String,
      required: true
    },

    accent: {
      type: String,
      default: 'green'
    }
  })
</script>


<template>
  <div class="section-label" :class="`accent-${accent}`">
    <span>§ {{ number }}</span>

    <p>{{ title }}</p>
  </div>
</template>


<style scoped>
  .section-label {
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.14em;
  }

  .section-label span {
    color: var(--green);
  }

  .section-label p {
    margin: 0;
    color: var(--grey);
  }

  .section-label.accent-yellow span {
    color: var(--yellow);
  }
</style>