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
   <!-- Brand -->
    <button class="brand" type="button" aria-label="Go to home" @click="emit('go-to', 'home')">
     <img class="brand-logo" src="@/assets/images/icon.png" alt="Softbox Infotech Solutions Ltd" />
      <span class="brand-name">
        SOFTBOX
      </span>
    </button>
   <!-- Header controls -->
    <div class="header-right">
     <div class="active-section" aria-label="Current section">
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
       <span class="menu-icon" aria-hidden="true">
          <i></i>
          <i></i>
        </span>
     </button>
   </div>
  </header>
</template>
<style scoped>
  /* =====================================================
   HEADER
===================================================== */
  .header {
    position: fixed;
    top: 0;
    left: 0;
   z-index: 1000;
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: var(--header-height);
   padding-inline: var(--page-padding);
    background: linear-gradient(to bottom,
       rgba(255, 255, 255, 0.98),
        rgba(255, 255, 255, 0));
    pointer-events: none;
 }
  .brand,
  .header-right {
    pointer-events: auto;
  }
  /* =====================================================
   BRAND
===================================================== */
  .brand {
    display: flex;
    align-items: center;
    gap: 0.8rem;
   padding: 0;
    border: 0;
    background: transparent;
    color: var(--text);
    cursor: pointer;
 }
  .brand-logo {
    width: 42px;
    height: 42px;
    object-fit: contain;
   transition:
      transform 0.3s ease,
      opacity 0.3s ease;
  }
  .brand:hover .brand-logo {
    transform: translateY(-1px);
  }
  .brand-name {
   color: var(--text);
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.14em;
   transition: color 0.3s ease;
  }

  .brand:hover .brand-name {
    color: var(--accent);
  }

/* =====================================================
   RIGHT SIDE
===================================================== */
  .header-right {
    display: flex;
    align-items: center;
    gap: 2rem;
 }
  .active-section {
    display: flex;
    align-items: center;
    gap: 0.6rem;
   color: var(--text-secondary);
    font-size: 0.6rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
 }
  .status-dot {
    width: 5px;
    height: 5px;
    border-radius: 50%;
   background: var(--accent);
    box-shadow:
     0 0 0 3px var(--accent-soft);
  }
  /* =====================================================
   MENU BUTTON
===================================================== */
  .menu-trigger {
    display: flex;
    align-items: center;
    gap: 1rem;
   height: 48px;
    padding: 0 1.1rem;
    border: 1px solid var(--border-strong);
    background: var(--text);
    color: var(--text-inverse);
    cursor: pointer;
    transition:
     background 0.3s ease,
      border-color 0.3s ease,
      color 0.3s ease;
 }
  .menu-trigger:hover {
   background: var(--accent);
    border-color: var(--accent);
  }
  .menu-text {
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
  }
  /* =====================================================
   MENU ICON
===================================================== */
  .menu-icon {
   position: relative;
    width: 18px;
   height: 12px;
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
  /* =====================================================
   OPEN STATE
===================================================== */
  .menu-trigger.open {
   background: var(--accent);
    border-color: var(--accent);
    color: var(--text-inverse);
  }
  .menu-trigger.open .menu-icon i:first-child {
    top: 6px;
    transform: rotate(45deg);
 }
  .menu-trigger.open .menu-icon i:last-child {
    top: 6px;
    transform: rotate(-45deg);
  }
  /* =====================================================
   MOBILE
===================================================== */
  @media (max-width: 600px) {
    .active-section {
      display: none;
   }
    .brand-name {
      font-size: 0.7rem;
    }
    .brand-logo {
      width: 38px;
      height: 38px;
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
