<script setup>
  import { ArrowDownRight, ArrowUpRight, Boxes, GraduationCap, Headphones } from 'lucide-vue-next';

  import SectionLabel from '@/components/SectionLabel.vue';

  defineEmits(['go-to']);
</script>

<template>
  <section class="home" id="home">
    <div class="hero">
      <!-- TOP META -->
      <div class="hero-meta">
        <div class="meta-left">
          <SectionLabel number="00" title="Business Technology" />
        </div>

        <div class="meta-right">
          <span>PORT HARCOURT / NIGERIA</span>
          <span class="meta-status">
            <i></i>
            AVAILABLE FOR PROJECTS
          </span>
        </div>
      </div>

      <!-- HERO CONTENT -->
      <div class="hero-content">
        <div class="hero-title">
          <div class="eyebrow">
            <span>SOFTBOX INFOTECH SOLUTIONS LTD</span>
            <span>EST. / BUSINESS SYSTEMS</span>
          </div>

          <h1>
            Technology
            <span>for better</span>
            business.
          </h1>

          <div class="hero-index">
            <span>00 / 04</span>
            <span>BUSINESS TECHNOLOGY</span>
          </div>
        </div>

        <div class="hero-side">
          <div class="side-line"></div>

          <p>Business management software, practical training and dependable technical support for modern organisations.
          </p>

          <button class="hero-button" type="button" @click="$emit('go-to', 'solutions')">
            <span>Explore solutions</span>

            <ArrowUpRight :size="18" :stroke-width="1.4" />
          </button>
        </div>
      </div>

      <!-- SERVICES -->
      <div class="hero-services">
        <!-- BUSINESS SOLUTIONS -->
        <button type="button" @click="$emit('go-to', 'solutions')">
          <span class="service-number">01</span>

          <div class="service-icon">
            <Boxes :size="24" :stroke-width="1.1" />
          </div>

          <div class="service-content">
            <span>BUSINESS SYSTEMS</span>

            <strong> Business Solutions </strong>
          </div>

          <ArrowUpRight class="service-arrow" :size="19" :stroke-width="1.3" />
        </button>

        <!-- TRAINING -->
        <button type="button" @click="$emit('go-to', 'services')">
          <span class="service-number">02</span>

          <div class="service-icon">
            <GraduationCap :size="24" :stroke-width="1.1" />
          </div>

          <div class="service-content">
            <span>PEOPLE / DEVELOPMENT</span>

            <strong> Training & Mentorship </strong>
          </div>

          <ArrowUpRight class="service-arrow" :size="19" :stroke-width="1.3" />
        </button>

        <!-- SUPPORT -->
        <button type="button" @click="$emit('go-to', 'services')">
          <span class="service-number">03</span>

          <div class="service-icon">
            <Headphones :size="24" :stroke-width="1.1" />
          </div>

          <div class="service-content">
            <span>TECHNICAL / SUPPORT</span>

            <strong> Support & Maintenance </strong>
          </div>

          <ArrowUpRight class="service-arrow" :size="19" :stroke-width="1.3" />
        </button>
      </div>

      <!-- BOTTOM -->
      <div class="hero-bottom">
        <button class="scroll" type="button" @click="$emit('go-to', 'about')">
          <span>SCROLL TO DISCOVER</span>

          <ArrowDownRight :size="17" :stroke-width="1.3" />
        </button>

        <span class="hero-location"> BUSINESS / SOFTWARE / SUPPORT </span>
      </div>
    </div>
  </section>
</template>

<style scoped>

  /* =====================================================
   HOME
===================================================== */
  .home {
    position: relative;
    min-height: 100svh;
    background: linear-gradient(90deg, transparent 0, transparent calc(100% - 1px), rgba(255, 255, 255, 0.025) calc(100% - 1px)), var(--black);
    overflow: hidden;
  }

  /* =====================================================
   TECHNICAL GRID
===================================================== */
  .home::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image: linear-gradient(rgba(255, 255, 255, 0.025) 1px, transparent 1px), linear-gradient(90deg, rgba(255, 255, 255, 0.025) 1px, transparent 1px);
    background-size: 80px 80px;
    mask-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.8), transparent 90%);
    pointer-events: none;
  }

  /* vertical technical line */
  .home::after {
    content: '';
    position: absolute;
    top: 0;
    bottom: 0;
    left: calc(50% + min(690px, 45vw));
    width: 1px;
    background: rgba(255, 255, 255, 0.045);
    pointer-events: none;
  }

  /* =====================================================
   HERO
===================================================== */
  .hero {
    position: relative;
    z-index: 1;
    width: min(calc(100% - (var(--page-padding) * 2)), var(--container));
    min-height: 100svh;
    margin-inline: auto;
    padding: calc(var(--header-height) + 2rem) 0 1.5rem;
    display: flex;
    flex-direction: column;
  }

  /* =====================================================
   META
===================================================== */
  .hero-meta {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    min-height: 55px;
  }

  .meta-right {
    display: flex;
    align-items: center;
    gap: 2rem;
    padding-top: 0.35rem;
  }

  .meta-right > span {
    color: var(--grey);
    font-size: 0.58rem;
    letter-spacing: 0.14em;
  }

  .meta-status {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    color: var(--green) !important;
  }

  .meta-status i {
    display: block;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--green);
    box-shadow: 0 0 10px rgba(57, 245, 154, 0.45);
  }

  /* =====================================================
   MAIN CONTENT
===================================================== */
  .hero-content {
    position: relative;
    flex: 1;
    display: grid;
    grid-template-columns: minmax(0, 1.8fr) minmax(260px, 0.55fr);
    align-items: center;
    gap: clamp(3rem, 7vw, 8rem);
    padding: 4rem 0 3rem;
  }

  /* =====================================================
   BACKGROUND NUMBER
===================================================== */
  .hero-content::before {
    content: '00';
    position: absolute;
    right: -1rem;
    top: 50%;
    transform: translateY(-52%);
    color: rgba(255, 255, 255, 0.025);
    font-size: clamp(14rem, 32vw, 32rem);
    font-weight: 700;
    line-height: 0.7;
    letter-spacing: -0.1em;
    pointer-events: none;
    user-select: none;
  }

  /* =====================================================
   TITLE
===================================================== */
  .hero-title {
    position: relative;
    z-index: 1;
  }

  .eyebrow {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin: 0 0 1.75rem;
    color: var(--green);
    font-size: 0.6rem;
    font-weight: 600;
    letter-spacing: 0.16em;
  }

  .eyebrow span:last-child {
    color: var(--grey-dark);
  }

  .hero-title h1 {
    max-width: 1050px;
    margin: 0;
    color: var(--white);
    font-size: clamp(4rem, 9.2vw, 9.5rem);
    font-weight: 500;
    line-height: 0.82;
    letter-spacing: -0.075em;
    text-transform: uppercase;
  }

  .hero-title h1 span {
    display: block;
    color: var(--green);
  }

  /* index */
  .hero-index {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    margin-top: 2rem;
  }

  .hero-index span {
    color: var(--grey-dark);
    font-size: 0.55rem;
    letter-spacing: 0.15em;
  }

  .hero-index span:first-child {
    color: var(--yellow);
  }

  /* =====================================================
   HERO SIDE
===================================================== */
  .hero-side {
    position: relative;
    z-index: 1;
    max-width: 360px;
    justify-self: end;
    padding-bottom: 1rem;
  }

  .side-line {
    width: 40px;
    height: 1px;
    margin-bottom: 1.5rem;
    background: var(--yellow);
  }

  .hero-side p {
    max-width: 340px;
    margin: 0 0 2rem;
    color: var(--grey);
    font-size: 0.9rem;
    line-height: 1.75;
  }

  /* button */
  .hero-button {
    display: inline-flex;
    align-items: center;
    gap: 1rem;
    padding: 0.9rem 1.2rem;
    border: 1px solid var(--green);
    border-radius: 0;
    background: transparent;
    color: var(--green);
    font: inherit;
    font-size: 0.65rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    cursor: pointer;
    transition:
      background 0.3s ease,
      color 0.3s ease;
  }

  .hero-button svg {
    transition: transform 0.3s ease;
  }

  .hero-button:hover {
    background: var(--green);
    color: var(--black);
  }

  .hero-button:hover svg {
    transform: translate(4px, -4px);
  }

  /* =====================================================
   SERVICES
===================================================== */
  .hero-services {
    position: relative;
    z-index: 2;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border-top: 1px solid var(--border);
    border-left: 1px solid var(--border);
  }

  .hero-services button {
    position: relative;
    min-height: 125px;
    padding: 1.25rem 1.4rem;
    border: 0;
    border-right: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    background: rgba(5, 5, 5, 0.75);
    color: var(--white);
    display: grid;
    grid-template-columns: 30px 45px 1fr 25px;
    align-items: center;
    gap: 0.75rem;
    text-align: left;
    cursor: pointer;
    transition:
      background 0.35s ease,
      color 0.35s ease,
      padding 0.35s ease;
  }

  .hero-services button::before {
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    width: 0;
    height: 2px;
    background: var(--green);
    transition: width 0.35s ease;
  }

  .hero-services button:nth-child(2)::before {
    background: var(--yellow);
  }

  .hero-services button:hover {
    background: var(--green);
    color: var(--black);
    padding-left: 1.8rem;
  }

  .hero-services button:nth-child(2):hover {
    background: var(--yellow);
  }

  .hero-services button:hover::before {
    width: 100%;
  }

  /* service number */
  .service-number {
    align-self: start;
    padding-top: 0.2rem;
    color: var(--grey-dark);
    font-size: 0.58rem;
    letter-spacing: 0.1em;
  }

  .hero-services button:hover .service-number {
    color: rgba(0, 0, 0, 0.55);
  }

  /* icon */
  .service-icon {
    display: grid;
    place-items: center;
    width: 42px;
    height: 42px;
    border: 1px solid var(--border-light);
    color: var(--green);
    transition:
      border-color 0.3s ease,
      color 0.3s ease;
  }

  .hero-services button:nth-child(2) .service-icon {
    color: var(--yellow);
  }

  .hero-services button:hover .service-icon {
    border-color: rgba(0, 0, 0, 0.3);
    color: var(--black) !important;
  }

  /* service content */
  .service-content {
    min-width: 0;
  }

  .service-content > span {
    display: block;
    margin-bottom: 0.35rem;
    color: var(--grey-dark);
    font-size: 0.52rem;
    letter-spacing: 0.13em;
  }

  .service-content strong {
    display: block;
    font-size: 0.85rem;
    font-weight: 500;
    line-height: 1.2;
  }

  .hero-services button:hover .service-content > span {
    color: rgba(0, 0, 0, 0.55);
  }

  /* arrow */
  .service-arrow {
    color: var(--yellow);
    transition:
      transform 0.3s ease,
      color 0.3s ease;
  }

  .hero-services button:hover .service-arrow {
    color: var(--black);
    transform: translate(4px, -4px);
  }

  /* =====================================================
   BOTTOM
===================================================== */
  .hero-bottom {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 1rem;
  }

  .scroll {
    display: flex;
    align-items: center;
    gap: 0.65rem;
    padding: 0;
    border: 0;
    background: transparent;
    color: var(--grey);
    font: inherit;
    font-size: 0.55rem;
    letter-spacing: 0.14em;
    cursor: pointer;
  }

  .scroll svg {
    color: var(--yellow);
    transition: transform 0.3s ease;
  }

  .scroll:hover {
    color: var(--white);
  }

  .scroll:hover svg {
    transform: translate(4px, 4px);
  }

  .hero-location {
    color: var(--grey-dark);
    font-size: 0.52rem;
    letter-spacing: 0.14em;
  }

  /* =====================================================
   TABLET
===================================================== */
  @media (max-width: 1000px) {
    .hero-content {
      grid-template-columns: 1fr 0.5fr;
      gap: 3rem;
    }

    .hero-title h1 {
      font-size: clamp(4rem, 9vw, 7rem);
    }

    .hero-services button {
      grid-template-columns: 28px 40px 1fr 20px;
      padding-inline: 1rem;
    }
  }

  /* =====================================================
   SMALL TABLET
===================================================== */
  @media (max-width: 850px) {
    .hero {
      padding-top: calc(var(--header-height) + 1.5rem);
    }

    .meta-status {
      display: none;
    }

    .hero-content {
      grid-template-columns: 1fr;
      gap: 2.5rem;
      padding-top: 5rem;
    }

    .hero-content::before {
      right: -1rem;
      top: 35%;
      font-size: 15rem;
    }

    .hero-side {
      justify-self: start;
      max-width: 520px;
    }

    .hero-services {
      grid-template-columns: 1fr;
    }

    .hero-services button {
      min-height: 100px;
    }
  }

  /* =====================================================
   MOBILE
===================================================== */
  @media (max-width: 600px) {
    .hero {
      width: min(calc(100% - (var(--page-padding) * 2)), var(--container));
      padding-bottom: 1rem;
    }

    .hero-meta {
      min-height: 45px;
    }

    .hero-meta .meta-left {
      width: 100%;
    }

    .hero-meta .meta-left :deep(.section-label) {
      width: 100%;
    }

    .hero-content {
      padding-top: 4rem;
    }

    .eyebrow {
      flex-direction: column;
      align-items: flex-start;
      gap: 0.5rem;
      margin-bottom: 1.5rem;
    }

    .hero-title h1 {
      font-size: clamp(3.3rem, 16vw, 5.4rem);
      line-height: 0.84;
    }

    .hero-content::before {
      top: 32%;
      font-size: 11rem;
    }

    .hero-index {
      margin-top: 1.5rem;
    }

    .hero-side p {
      font-size: 0.82rem;
    }

    .hero-services button {
      grid-template-columns: 25px 42px 1fr 20px;
      min-height: 88px;
      padding: 1rem;
    }

    .service-icon {
      width: 38px;
      height: 38px;
    }

    .service-content strong {
      font-size: 0.78rem;
    }

    .service-content > span {
      font-size: 0.48rem;
    }

    .hero-location {
      display: none;
    }

    .hero-bottom {
      padding-top: 1rem;
    }
  }
</style>