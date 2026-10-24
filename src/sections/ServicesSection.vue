<script setup>
  import { ArrowUpRight, BriefcaseBusiness, GraduationCap, UserSearch, Wrench } from 'lucide-vue-next';

  import SectionLabel from '@/components/SectionLabel.vue';

  defineEmits(['go-to']);

  const services = [
    {
      number: '01',
      shortTitle: 'KNOWLEDGE',
      title: 'Training & Mentorship',
      icon: GraduationCap,
      accent: 'green',
      description: 'Practical training and mentorship that helps individuals and organisations confidently use business management software and get more value from their technology.',
    },
    {
      number: '02',
      shortTitle: 'CONTINUITY',
      title: 'Support & Maintenance',
      icon: Wrench,
      accent: 'yellow',
      description: 'Dependable technical assistance and ongoing maintenance designed to keep your business software and technology solutions working effectively.',
    },
    {
      number: '03',
      shortTitle: 'TALENT',
      title: 'Specialized Recruitment',
      icon: UserSearch,
      accent: 'green',
      description: 'Specialized recruitment services focused on identifying and connecting organisations with qualified professionals for finance and procurement roles.',
    },
    {
      number: '04',
      shortTitle: 'WORKFORCE',
      title: 'Personnel Outsourcing',
      icon: BriefcaseBusiness,
      accent: 'yellow',
      description: 'Flexible outsourcing of skilled finance and procurement personnel to support business operations, strengthen teams and meet changing workforce requirements.',
    },
  ];
</script>

<template>
  <section class="services site-section" id="services">
    <div class="section-inner">
      <!-- Section heading -->
      <div class="services-heading">
        <div class="heading-meta">
          <SectionLabel number="03" title="Services" accent="yellow" />

          <span class="heading-code"> PEOPLE / SUPPORT / GROWTH </span>
        </div>

        <div class="heading-content">
          <span class="ghost-number">03</span>

          <p class="eyebrow">BEYOND IMPLEMENTATION</p>

          <h2>
            Beyond
            <span>software.</span>
          </h2>

          <p class="intro">Technology works best when it is supported by capable people. From training and technical
            support to specialized recruitment and personnel outsourcing, we help businesses build the knowledge,
            systems and teams they need to perform.</p>
        </div>
      </div>

      <!-- Services -->
      <div class="service-list">
        <article v-for="service in services" :key="service.number" class="service-row" :class="service.accent">
          <div class="service-number">
            {{ service.number }}
          </div>

          <div class="service-category">
            <span>{{ service.shortTitle }}</span>
          </div>

          <div class="service-icon">
            <component :is="service.icon" :size="30" :stroke-width="1.25" />
          </div>

          <div class="service-content">
            <h3>{{ service.title }}</h3>

            <p>
              {{ service.description }}
            </p>
          </div>

          <button class="service-action" type="button" @click="$emit('go-to', 'contact')"
            :aria-label="`Enquire about ${service.title}`">
            <span>ENQUIRE</span>
            <ArrowUpRight :size="16" />
          </button>
        </article>
      </div>

      <!-- Approach -->
      <div class="approach">
        <div class="approach-label">
          <span>03 / 01</span>
          <p>OUR APPROACH</p>
        </div>

        <div class="approach-content">
          <p>
            Technology is only
            <span>part of the solution.</span>
          </p>

          <div class="approach-note">
            <span class="line"></span>

            <p>We combine business technology, practical knowledge, ongoing support and specialized talent to help
              organisations operate with greater confidence.</p>
          </div>
        </div>
      </div>

      <!-- CTA -->
      <div class="services-cta">
        <div class="cta-meta">
          <span>READY TO TALK?</span>
          <span>03 / 02</span>
        </div>

        <div class="cta-main">
          <h3>
            Let's discuss your
            <span>business requirements.</span>
          </h3>

          <button class="cta-button" type="button" @click="$emit('go-to', 'contact')">
            <span>Talk to Softbox</span>
            <ArrowUpRight :size="18" />
          </button>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
  .services {
    position: relative;
    background: linear-gradient(90deg, transparent calc(50% - 0.5px), rgba(255, 255, 255, 0.035) calc(50% - 0.5px), rgba(255, 255, 255, 0.035) 50%, transparent 50%), var(--black-soft);
    color: var(--white);
    overflow: hidden;
  }

  /* Technical grid */
  .services::before {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    background-image: linear-gradient(rgba(255, 255, 255, 0.018) 1px, transparent 1px), linear-gradient(90deg, rgba(255, 255, 255, 0.018) 1px, transparent 1px);
    background-size: 80px 80px;
    mask-image: linear-gradient(to bottom, black, transparent 48%);
  }

  .section-inner {
    position: relative;
    z-index: 1;
    width: min(100%, var(--container));
    margin: 0 auto;
    padding: var(--section-space) var(--page-padding);
  }

  /* =========================
   HEADING
========================= */
  .services-heading {
    display: grid;
    grid-template-columns: 150px minmax(0, 1fr);
    gap: clamp(2rem, 5vw, 6rem);
    min-height: 500px;
    padding-bottom: clamp(3rem, 6vw, 6rem);
    border-bottom: 1px solid var(--border);
  }

  .heading-meta {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 2rem;
  }

  .heading-code {
    color: var(--grey-dark);
    font-family: monospace;
    font-size: 0.58rem;
    line-height: 1.6;
    letter-spacing: 0.13em;
    writing-mode: vertical-rl;
    transform: rotate(180deg);
  }

  .heading-content {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-start;
    max-width: 1050px;
  }

  .ghost-number {
    position: absolute;
    top: -2rem;
    right: 0;
    z-index: -1;
    color: rgba(255, 255, 255, 0.025);
    font-size: clamp(10rem, 25vw, 24rem);
    font-weight: 800;
    line-height: 0.75;
    letter-spacing: -0.09em;
    user-select: none;
  }

  .eyebrow {
    margin: 0 0 1.2rem;
    color: var(--yellow);
    font-size: 0.62rem;
    font-weight: 800;
    letter-spacing: 0.18em;
  }

  .heading-content h2 {
    max-width: 850px;
    margin: 0;
    font-size: clamp(4rem, 10vw, 9.5rem);
    font-weight: 800;
    line-height: 0.82;
    letter-spacing: -0.065em;
    text-transform: uppercase;
  }

  .heading-content h2 span {
    display: block;
    color: var(--green);
  }

  .intro {
    max-width: 600px;
    margin: 2.2rem 0 0;
    color: var(--grey);
    font-size: clamp(0.9rem, 1.1vw, 1rem);
    line-height: 1.8;
  }

  /* =========================
   SERVICES
========================= */
  .service-list {
    border-bottom: 1px solid var(--border);
  }

  .service-row {
    position: relative;
    display: grid;
    grid-template-columns: 70px minmax(100px, 0.55fr) 70px minmax(280px, 1.5fr) 110px;
    align-items: center;
    gap: clamp(1rem, 2.5vw, 3rem);
    min-height: 190px;
    padding: 2rem 0;
    border-bottom: 1px solid var(--border);
    transition:
      padding 0.35s var(--ease),
      background 0.35s ease;
  }

  .service-row:last-child {
    border-bottom: 0;
  }

  .service-row::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 2px;
    height: 0;
    background: var(--green);
    transition: height 0.4s var(--ease);
  }

  .service-row.yellow::before {
    background: var(--yellow);
  }

  .service-row:hover {
    padding-left: 1.2rem;
    padding-right: 1.2rem;
    background: rgba(255, 255, 255, 0.018);
  }

  .service-row:hover::before {
    height: 100%;
  }

  /* Number */
  .service-number {
    align-self: start;
    padding-top: 0.2rem;
    color: var(--grey-dark);
    font-family: monospace;
    font-size: 0.7rem;
    letter-spacing: 0.12em;
  }

  /* Category */
  .service-category {
    align-self: start;
    padding-top: 0.15rem;
  }

  .service-category span {
    color: var(--grey-dark);
    font-size: 0.58rem;
    font-weight: 800;
    letter-spacing: 0.15em;
  }

  .service-row.green .service-category span {
    color: var(--green);
  }

  .service-row.yellow .service-category span {
    color: var(--yellow);
  }

  /* Icon */
  .service-icon {
    display: grid;
    place-items: center;
    width: 54px;
    height: 54px;
    border: 1px solid var(--border-light);
    color: var(--green);
    transition:
      border-color 0.3s ease,
      transform 0.3s var(--ease);
  }

  .service-row.yellow .service-icon {
    color: var(--yellow);
  }

  .service-row:hover .service-icon {
    transform: rotate(-4deg);
    border-color: currentColor;
  }

  /* Content */
  .service-content {
    max-width: 620px;
  }

  .service-content h3 {
    margin: 0 0 0.8rem;
    color: var(--white);
    font-size: clamp(1.5rem, 2.8vw, 2.8rem);
    font-weight: 700;
    line-height: 1;
    letter-spacing: -0.04em;
  }

  .service-content p {
    max-width: 570px;
    margin: 0;
    color: var(--grey);
    font-size: 0.82rem;
    line-height: 1.7;
  }

  /* Action */
  .service-action {
    display: inline-flex;
    align-items: center;
    justify-content: flex-end;
    gap: 0.65rem;
    padding: 0;
    border: 0;
    background: transparent;
    color: var(--grey-dark);
    cursor: pointer;
    font-family: inherit;
    font-size: 0.58rem;
    font-weight: 800;
    letter-spacing: 0.13em;
    transition:
      color 0.25s ease,
      gap 0.25s ease;
  }

  .service-action svg {
    color: var(--green);
  }

  .service-row.yellow .service-action svg {
    color: var(--yellow);
  }

  .service-action:hover {
    gap: 0.9rem;
    color: var(--white);
  }

  /* =========================
   APPROACH
========================= */
  .approach {
    display: grid;
    grid-template-columns: 150px minmax(0, 1fr);
    gap: clamp(2rem, 5vw, 6rem);
    padding: clamp(4rem, 8vw, 8rem) 0;
    border-bottom: 1px solid var(--border);
  }

  .approach-label span {
    display: block;
    margin-bottom: 0.5rem;
    color: var(--yellow);
    font-family: monospace;
    font-size: 0.6rem;
  }

  .approach-label p {
    margin: 0;
    color: var(--grey-dark);
    font-size: 0.58rem;
    font-weight: 800;
    letter-spacing: 0.16em;
  }

  .approach-content > p {
    max-width: 850px;
    margin: 0;
    color: var(--white);
    font-size: clamp(2.5rem, 5vw, 5.5rem);
    font-weight: 700;
    line-height: 0.98;
    letter-spacing: -0.055em;
  }

  .approach-content > p span {
    color: var(--green);
  }

  .approach-note {
    display: grid;
    grid-template-columns: 50px minmax(0, 440px);
    gap: 1.5rem;
    margin-top: 2.5rem;
  }

  .approach-note .line {
    width: 100%;
    height: 1px;
    margin-top: 0.55rem;
    background: var(--yellow);
  }

  .approach-note p {
    margin: 0;
    color: var(--grey);
    font-size: 0.82rem;
    line-height: 1.7;
  }

  /* =========================
   CTA
========================= */
  .services-cta {
    padding-top: clamp(3rem, 6vw, 6rem);
  }

  .cta-meta {
    display: flex;
    justify-content: space-between;
    padding-bottom: 1rem;
    border-bottom: 1px solid var(--border);
    color: var(--grey-dark);
    font-family: monospace;
    font-size: 0.58rem;
    letter-spacing: 0.13em;
  }

  .cta-meta span:first-child {
    color: var(--yellow);
  }

  .cta-main {
    display: grid;
    grid-template-columns: minmax(0, 1fr) auto;
    align-items: end;
    gap: 3rem;
    padding-top: 2.5rem;
  }

  .cta-main h3 {
    max-width: 800px;
    margin: 0;
    font-size: clamp(2.5rem, 5.5vw, 6rem);
    font-weight: 700;
    line-height: 0.92;
    letter-spacing: -0.055em;
  }

  .cta-main h3 span {
    display: block;
    color: var(--green);
  }

  .cta-button {
    display: inline-flex;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
    min-width: 210px;
    padding: 1rem 1.1rem;
    border: 1px solid var(--yellow);
    border-radius: 0;
    background: transparent;
    color: var(--white);
    cursor: pointer;
    font-family: inherit;
    font-size: 0.68rem;
    font-weight: 800;
    letter-spacing: 0.08em;
    transition:
      background 0.3s ease,
      color 0.3s ease;
  }

  .cta-button svg {
    color: var(--yellow);
  }

  .cta-button:hover {
    background: var(--yellow);
    color: var(--black);
  }

  .cta-button:hover svg {
    color: var(--black);
  }

  /* =========================
   RESPONSIVE
========================= */
  @media (max-width: 1000px) {
    .service-row {
      grid-template-columns: 50px 90px 60px minmax(250px, 1fr);
      gap: 1.5rem;
    }

    .service-action {
      grid-column: 4;
      justify-content: flex-start;
    }
  }

  @media (max-width: 760px) {

    .services-heading,
    .approach {
      grid-template-columns: 1fr;
    }

    .services-heading {
      min-height: auto;
    }

    .heading-meta {
      flex-direction: row;
      align-items: center;
    }

    .heading-code {
      writing-mode: initial;
      transform: none;
    }

    .heading-content {
      padding-top: 4rem;
    }

    .ghost-number {
      top: 0;
      font-size: 11rem;
    }

    .heading-content h2 {
      font-size: clamp(3.5rem, 16vw, 7rem);
    }

    .service-row {
      grid-template-columns: 45px 1fr auto;
      gap: 1rem;
      min-height: auto;
      padding: 2rem 0;
    }

    .service-number {
      grid-column: 1;
      grid-row: 1;
    }

    .service-category {
      grid-column: 2;
      grid-row: 1;
    }

    .service-icon {
      grid-column: 3;
      grid-row: 1 / 3;
      width: 48px;
      height: 48px;
    }

    .service-content {
      grid-column: 2 / 4;
      grid-row: 2;
      padding-top: 0.7rem;
    }

    .service-action {
      grid-column: 2 / 4;
      grid-row: 3;
      justify-content: flex-start;
      margin-top: 0.6rem;
    }

    .service-row:hover {
      padding-left: 0.7rem;
      padding-right: 0.7rem;
    }

    .approach-content > p {
      font-size: clamp(2.4rem, 10vw, 4.5rem);
    }

    .cta-main {
      grid-template-columns: 1fr;
      align-items: start;
    }

    .cta-button {
      width: 100%;
    }
  }

  @media (max-width: 480px) {
    .section-inner {
      padding-left: var(--page-padding);
      padding-right: var(--page-padding);
    }

    .heading-content {
      padding-top: 3rem;
    }

    .heading-content h2 {
      font-size: clamp(3.1rem, 17vw, 5rem);
    }

    .intro {
      font-size: 0.82rem;
    }

    .service-row {
      grid-template-columns: 36px 1fr auto;
    }

    .service-icon {
      width: 42px;
      height: 42px;
    }

    .service-icon svg {
      width: 23px;
      height: 23px;
    }

    .service-content h3 {
      font-size: 1.65rem;
    }

    .service-content p {
      font-size: 0.78rem;
    }

    .approach-note {
      grid-template-columns: 30px 1fr;
      gap: 1rem;
    }

    .cta-main h3 {
      font-size: clamp(2.4rem, 12vw, 4rem);
    }
  }
</style>