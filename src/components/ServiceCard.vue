<script setup>
  import { ArrowUpRight } from 'lucide-vue-next';

  defineProps({
    number: String,
    title: String,
    description: String,
    icon: [Object, Function],
    accent: String
  })
</script>


<template>
  <article class="service-card" :class="accent">

    <div class="top">

      <span>
        {{ number }}
      </span>

      <ArrowUpRight :size="18" />

    </div>


    <div class="visual">

      <component :is="icon" :size="48" :stroke-width="1.1" />

    </div>


    <div class="content">

      <h3>
        {{ title }}
      </h3>

      <p>
        {{ description }}
      </p>

    </div>

  </article>
</template>


<style scoped>
  .service-card {
    min-height: 380px;
    padding: 1.75rem;
    border: 1px solid var(--border);
    border-radius: var(--radius);
    display: flex;
    flex-direction: column;
    transition:
      transform 0.4s var(--ease),
      border-color 0.3s ease;
  }

  .service-card:hover {
    transform: translateY(-5px);
    border-color: var(--green);
  }

  .top {
    display: flex;
    justify-content: space-between;
    color: var(--grey);
    font-size: 0.6rem;
  }

  .top svg {
    color: var(--yellow);
  }

  .visual {
    width: 100%;
    flex: 1;
    display: grid;
    place-items: center;
    color: var(--green);
  }

  .visual svg {
    width: 70px;
    height: 70px;
  }

  .content {
    padding-top: 1.5rem;
    border-top: 1px solid var(--border);
  }

  h3 {
    margin-bottom: 1rem;
    font-size: clamp(1.8rem,
        3vw,
        3rem);
    font-weight: 400;
    line-height: 1;
    letter-spacing: -0.04em;
  }

  p {
    max-width: 480px;
    margin: 0;
    color: var(--grey);
    font-size: 0.82rem;
    line-height: 1.7;
  }

  .yellow .visual {
    color: var(--yellow);
  }
</style>