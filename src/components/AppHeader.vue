<script setup>
  defineProps({
    menuOpen: {
      type: Boolean,
      default: false
    },

    activeSection: {
      type: String,
      default: 'home'
    }
  })


  const emit = defineEmits([
    'toggle-menu',
    'go-to'
  ])
</script>


<template>
  <header class="header">

    <button class="brand" type="button" aria-label="Go to home" @click="emit('go-to', 'home')">
      <!-- <span class="brand-mark">
        <img src="@/assets/images/softbox-logo.png" alt="Softbox Infotech Solutions Ltd" />
      </span> -->

      <img class="brand-logo" src="@/assets/images/icon.png" alt="Softbox Infotech Solutions Ltd" />

      <span class="brand-name">
        SOFTBOX
      </span>
    </button>


    <div class="header-right">

      <div class="active-section">
        <span class="status-dot"></span>

        <span>
          {{ activeSection }}
        </span>
      </div>


      <button class="menu-trigger" type="button" :class="{ open: menuOpen }" :aria-expanded="menuOpen"
        aria-label="Toggle navigation menu" @click="emit('toggle-menu')">
        <span class="menu-text">
          {{ menuOpen ? 'Close' : 'Menu' }}
        </span>

        <span class="menu-icon">
          <i></i>
          <i></i>
        </span>
      </button>

    </div>

  </header>
</template>


<style scoped>
  .header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: var(--header-height);
    padding-inline: var(--page-padding);
    display: flex;
    align-items: center;
    justify-content: space-between;
    z-index: 1000;
    background: linear-gradient(to bottom,
        rgba(5, 5, 5, 0.95),
        rgba(5, 5, 5, 0));
    pointer-events: none;
  }

  .brand,
  .header-right {
    pointer-events: auto;
  }

  /* BRAND */
  .brand {
    padding: 0;
    border: 0;
    background: transparent;
    color: var(--white);
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }

  .brand-mark {
    width: 35px;
    height: 35px;
    border: 1px solid var(--green);
    display: grid;
    place-items: center;
    color: var(--green);
    font-size: 0.8rem;
    font-weight: 700;
  }

  .brand-logo {
    width: 42px;
    height: 42px;
    object-fit: contain;
  }

  .brand-name {
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.14em;
  }

  /* RIGHT */
  .header-right {
    display: flex;
    align-items: center;
    gap: 2rem;
  }

  .active-section {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    color: var(--grey);
    font-size: 0.6rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
  }

  .status-dot {
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--green);
    box-shadow:
      0 0 10px var(--green);
  }

  /* MENU */
  .menu-trigger {
    height: 48px;
    padding: 0 1.1rem;
    border: 1px solid var(--border-light);
    background: var(--black);
    color: var(--white);
    display: flex;
    align-items: center;
    gap: 1rem;
    transition:
      border-color 0.3s ease,
      color 0.3s ease;
  }

  .menu-trigger:hover {
    border-color: var(--green);
  }

  .menu-text {
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
  }

  .menu-icon {
    width: 18px;
    height: 12px;
    position: relative;
  }

  .menu-icon i {
    position: absolute;
    left: 0;
    width: 100%;
    height: 1px;
    background: currentColor;
    transition:
      transform 0.4s var(--ease),
      top 0.4s var(--ease);
  }

  .menu-icon i:first-child {
    top: 3px;
  }

  .menu-icon i:last-child {
    top: 9px;
  }

  .menu-trigger.open {
    border-color: var(--yellow);
    color: var(--yellow);
  }

  .menu-trigger.open .menu-icon i:first-child {
    top: 6px;
    transform: rotate(45deg);
  }

  .menu-trigger.open .menu-icon i:last-child {
    top: 6px;
    transform: rotate(-45deg);
  }

  @media (max-width: 600px) {
    .active-section {
      display: none;
    }

    .brand-name {
      font-size: 0.7rem;
    }

    .menu-text {
      display: none;
    }

    .menu-trigger {
      width: 48px;
      padding: 0;
      justify-content: center;
    }
  }
</style>