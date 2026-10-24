<script setup>
  defineProps({
    open: Boolean,

    sections: {
      type: Array,
      required: true
    },

    activeSection: String
  })


  const emit = defineEmits([
    'close',
    'go-to'
  ])
</script>


<template>
  <Transition name="menu">

    <div v-if="open" class="menu-overlay">

      <div class="menu-top">
        <p>
          NAVIGATION / SOFTBOX
        </p>
      </div>


      <nav class="navigation">

        <button v-for="section in sections" :key="section.id" type="button" class="nav-link" :class="{
          active:
            activeSection === section.id
        }" @click="emit('go-to', section.id)">

          <span class="number">
            {{ section.number }}
          </span>

          <span class="name">
            {{ section.name }}
          </span>

          <span class="arrow">
            ↗
          </span>

        </button>

      </nav>


      <div class="menu-footer">

        <div>
          <span>LOCATION</span>

          <p>
            Port Harcourt<br>
            Rivers State, Nigeria
          </p>
        </div>


        <div>
          <span>CONTACT</span>

          <p>
            08026754712<br>
            07031093053
          </p>
        </div>

      </div>

    </div>

  </Transition>
</template>


<style scoped>
  .menu-overlay {
    position: fixed;
    inset: 0;
    z-index: 900;
    padding:
      calc(var(--header-height) + 2rem) var(--page-padding) 3rem;
    background: var(--black);
    display: flex;
    flex-direction: column;
    overflow-y: auto;
  }

  .menu-overlay::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg,
        var(--green),
        var(--cyan),
        var(--yellow));
  }

  .menu-top {
    width: min(100%, var(--container));
    margin-inline: auto;
  }

  .menu-top p {
    color: var(--grey);
    font-size: 0.6rem;
    letter-spacing: 0.15em;
  }

  /* NAV */
  .navigation {
    width: min(100%, var(--container));
    margin:
      auto auto;
  }

  .nav-link {
    width: 100%;
    padding: 0.7rem 0;
    border: 0;
    border-top: 1px solid var(--border);
    background: transparent;
    color: var(--white);
    display: grid;
    grid-template-columns:
      80px 1fr auto;
    align-items: center;
    text-align: left;
    transition:
      padding 0.4s var(--ease),
      border-color 0.3s ease;
  }

  .nav-link:last-child {
    border-bottom: 1px solid var(--border);
  }

  .number {
    color: var(--green);
    font-size: 0.65rem;
    letter-spacing: 0.12em;
  }

  .name {
    font-size: clamp(2.7rem,
        6vw,
        6.5rem);
    font-weight: 500;
    line-height: 0.95;
    letter-spacing: -0.06em;
    text-transform: uppercase;
    transition:
      color 0.3s ease,
      transform 0.4s var(--ease);
  }

  .arrow {
    color: var(--yellow);
    font-size: 1.8rem;
    opacity: 0;
    transform: translateX(-20px);
    transition: 0.4s var(--ease);
  }

  .nav-link:hover {
    padding-left: 1rem;
    border-color: var(--green);
  }

  .nav-link:hover .name {
    color: var(--green);
  }

  .nav-link:hover .arrow {
    opacity: 1;
    transform: translateX(0);
  }

  .nav-link.active {
    border-color: var(--yellow);
  }

  .nav-link.active .number,
  .nav-link.active .name {
    color: var(--yellow);
  }

  /* FOOTER */
  .menu-footer {
    width: min(100%, var(--container));
    margin-inline: auto;
    padding-top: 2rem;
    display: flex;
    gap: 5rem;
  }

  .menu-footer span {
    color: var(--green);
    font-size: 0.55rem;
    letter-spacing: 0.15em;
  }

  .menu-footer p {
    margin: 0.5rem 0 0;
    color: var(--grey);
    font-size: 0.75rem;
    line-height: 1.7;
  }

  /* TRANSITION */
  .menu-enter-active,
  .menu-leave-active {
    transition:
      transform 0.7s var(--ease);
  }

  .menu-enter-from,
  .menu-leave-to {
    transform: translateY(-100%);
  }

  @media (max-width: 768px) {
    .nav-link {
      grid-template-columns:
        40px 1fr auto;
    }

    .name {
      font-size: clamp(2.4rem,
          13vw,
          4.5rem);
    }

    .menu-footer {
      gap: 3rem;
      flex-wrap: wrap;
    }
  }
</style>