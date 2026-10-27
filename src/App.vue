<script setup>
  import AppHeader from '@/components/AppHeader.vue';
  import AppMenu from '@/components/AppMenu.vue';
  import AboutSection from '@/sections/AboutSection.vue';
  import ContactSection from '@/sections/ContactSection.vue';
  import HomeSection from '@/sections/HomeSection.vue';
  import ServicesSection from '@/sections/ServicesSection.vue';
  import SolutionsSection from '@/sections/SolutionsSection.vue';
  import { onBeforeUnmount, onMounted, ref } from 'vue';
  const menuOpen = ref(false)
  const activeSection = ref('home')
  const sections = [
    {
      id: 'home',
      number: '00',
      name: 'Home'
    },
    {
      id: 'about',
      number: '01',
      name: 'About'
    },
    {
      id: 'solutions',
      number: '02',
      name: 'Solutions'
    },
    {
      id: 'services',
      number: '03',
      name: 'Services'
    },
    {
      id: 'contact',
      number: '04',
      name: 'Contact'
    }
  ]
  let observer = null
  const toggleMenu = () => {
    menuOpen.value = !menuOpen.value
    document.body.classList.toggle(
      'menu-open',
      menuOpen.value
    )
  }
  const closeMenu = () => {
    menuOpen.value = false
    document.body.classList.remove('menu-open')
  }
  const goToSection = (id) => {
    closeMenu()
    const section = document.getElementById(id)
    if (!section) return
    section.scrollIntoView({
      behavior: 'smooth',
      block: 'start'
    })
  }
  onMounted(() => {
    const elements = sections
      .map((section) => document.getElementById(section.id))
      .filter(Boolean)
    observer = new IntersectionObserver(
      (entries) => {
        const visibleEntry = entries
          .filter((entry) => entry.isIntersecting)
          .sort(
            (a, b) =>
              b.intersectionRatio - a.intersectionRatio
          )[0]
        if (visibleEntry) {
          activeSection.value = visibleEntry.target.id
        }
      },
      {
        rootMargin: '-35% 0px -55% 0px',
        threshold: [0, 0.1, 0.25, 0.5]
      }
    )
    elements.forEach((element) => {
      observer.observe(element)
    })
  })
  onBeforeUnmount(() => {
    observer?.disconnect()
    document.body.classList.remove('menu-open')
  })
</script>
<template>
  <div class="site">
    <AppHeader :menu-open="menuOpen" :active-section="activeSection" @toggle-menu="toggleMenu" @go-to="goToSection" />
    <AppMenu :open="menuOpen" :sections="sections" :active-section="activeSection" @close="closeMenu"
      @go-to="goToSection" />
    <main>
      <HomeSection id="home" @go-to="goToSection" />
      <AboutSection id="about" />
      <SolutionsSection id="solutions" />
      <ServicesSection id="services" @go-to="goToSection" />
      <ContactSection id="contact" />
    </main>
  </div>
</template>
<style scoped>
  .site {
    width: 100%;
    min-height: 100vh;
    background: var(--bg);
    color: var(--text);
  }
</style>