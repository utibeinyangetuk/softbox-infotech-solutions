<script setup>
  import { ArrowUpRight } from 'lucide-vue-next';

  defineProps({
    number: String,
    name: String,
    description: String,

    icon: {
      type: [Object, Function],
      required: true
    }
  })
</script>


<template>
  <article class="software-card">

    <span class="number">
      {{ number }}
    </span>


    <div class="icon">
      <component :is="icon" :size="24" :stroke-width="1.5" />
    </div>


    <div class="content">

      <h3>
        {{ name }}
      </h3>

      <p>
        {{ description }}
      </p>

    </div>


    <ArrowUpRight class="arrow" :size="20" />

  </article>
</template>


<style scoped>
  .software-card {
    min-height: 135px;
    padding: 1.4rem;
    border-bottom: 1px solid var(--border);
    display: grid;
    grid-template-columns:
      45px 55px 1fr auto;
    gap: 1rem;
    align-items: center;
    transition:
      background 0.3s ease,
      padding 0.3s ease;
  }

  .software-card:first-child {
    border-top: 1px solid var(--border);
  }

  .number {
    color: var(--grey);
    font-size: 0.55rem;
  }

  .icon {
    width: 48px;
    height: 48px;
    border: 1px solid var(--border);
    border-radius: 50%;
    display: grid;
    place-items: center;
    color: var(--green);
    transition: 0.3s ease;
  }

  .content h3 {
    margin: 0;
    font-size: clamp(1.3rem,
        2.3vw,
        2.1rem);
    font-weight: 400;
    letter-spacing: -0.035em;
  }

  .content p {
    max-width: 550px;
    margin:
      0.35rem 0 0;
    color: var(--grey);
    font-size: 0.78rem;
    line-height: 1.6;
  }

  .arrow {
    color: var(--yellow);
    opacity: 0;
    transform: translateX(-8px);
    transition: 0.3s ease;
  }

  .software-card:hover {
    padding-left: 2rem;
    background: var(--black-card);
  }

  .software-card:hover .icon {
    background: var(--green);
    border-color: var(--green);
    color: #000;
  }

  .software-card:hover .arrow {
    opacity: 1;
    transform: translateX(0);
  }

  @media (max-width: 600px) {
    .software-card {
      grid-template-columns:
        30px 45px 1fr;
      padding-inline: 0;
    }

    .icon {
      width: 40px;
      height: 40px;
    }

    .arrow {
      display: none;
    }

    .content p {
      font-size: 0.72rem;
    }
  }
</style>