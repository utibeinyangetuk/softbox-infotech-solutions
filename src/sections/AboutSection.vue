<script setup>
  import {
    ArrowUpRight,
    Check,
    Cpu,
    LineChart,
    UsersRound,
    Zap
  } from 'lucide-vue-next';

  import SectionLabel from '@/components/SectionLabel.vue';

  const benefits = [
    {
      title: 'Work smarter',
      text: 'Simplify everyday business processes with systems designed around how your organisation actually works.',
      icon: Zap
    },
    {
      title: 'See the bigger picture',
      text: 'Bring important business information together so you can make better and faster decisions.',
      icon: LineChart
    },
    {
      title: 'Build with confidence',
      text: 'Get the training, guidance and support your team needs to get the most from your technology.',
      icon: UsersRound
    }
  ]

  const capabilities = [
    'Business management software',
    'Accounting & financial systems',
    'ERP & inventory solutions',
    'Retail & supermarket systems',
    'HR management software',
    'Training & ongoing support'
  ]
</script>

<template>
  <section id="about" class="about-section">

    <div class="about-inner">

      <!-- SECTION HEADER -->
      <div class="about-header">

        <SectionLabel number="01" text="ABOUT SOFTBOX" />

        <div class="about-heading">
          <span class="muted">Technology should</span>
          <span>make business</span>
          <span class="accent">better.</span>
        </div>

      </div>


      <!-- INTRO -->
      <div class="about-intro">

        <div class="about-intro-mark">
          <Cpu :size="22" :stroke-width="1.4" />
        </div>

        <div class="about-intro-content">

          <p class="lead">
            Softbox Infotech Solutions Ltd helps businesses choose,
            implement and use technology that makes everyday operations
            simpler, smarter and more productive.
          </p>

          <div class="intro-bottom">

            <p>
              We work with organisations that want more from their
              business systems — from accounting and ERP to inventory,
              retail and HR management.
            </p>

            <p>
              Our approach goes beyond simply supplying software.
              We help businesses find the right solution, understand it,
              use it effectively and keep it working as their needs grow.
            </p>

          </div>

        </div>

      </div>


      <!-- VALUE STATEMENT -->
      <div class="about-statement">

        <div class="statement-line"></div>

        <div>
          <span class="statement-label">OUR APPROACH</span>

          <h3>
            The right technology.
            <br />
            The right people.
            <br />
            <strong>The right support.</strong>
          </h3>
        </div>

        <ArrowUpRight class="statement-arrow" :size="34" :stroke-width="1.2" />

      </div>


      <!-- BENEFITS -->
      <div class="about-benefits">

        <article v-for="(benefit, index) in benefits" :key="benefit.title" class="benefit-card">

          <div class="benefit-top">
            <span class="benefit-number">
              0{{ index + 1 }}
            </span>

            <component :is="benefit.icon" :size="21" :stroke-width="1.4" />
          </div>

          <div class="benefit-content">
            <h3>{{ benefit.title }}</h3>

            <p>
              {{ benefit.text }}
            </p>
          </div>

        </article>

      </div>


      <!-- CAPABILITIES -->
      <div class="about-capabilities">

        <div class="capabilities-heading">

          <span>WHAT WE DO</span>

          <p>
            Practical technology solutions for the
            systems behind your business.
          </p>

        </div>


        <div class="capabilities-list">

          <div v-for="(capability, index) in capabilities" :key="capability" class="capability-item">

            <span class="capability-number">
              {{ String(index + 1).padStart(2, '0') }}
            </span>

            <span class="capability-name">
              {{ capability }}
            </span>

            <Check :size="17" :stroke-width="1.5" />

          </div>

        </div>

      </div>


      <!-- BOTTOM CTA -->
      <div class="about-bottom">

        <div class="bottom-copy">
          <span>BUILT AROUND YOUR BUSINESS</span>

          <h3>
            Better systems.
            <br />
            Better business.
          </h3>
        </div>

        <a href="#contact" class="about-cta">
          <span>Let's work together</span>

          <ArrowUpRight :size="19" :stroke-width="1.5" />
        </a>

      </div>

    </div>

  </section>
</template>

<style scoped>

  /* =========================================================
SOFTBOX — ABOUT SECTION
Editorial / Technology / Premium
========================================================= */
  .about-section {
    position: relative;
    overflow: hidden;
    background:
      linear-gradient(90deg,
        transparent 49.95%,
        rgba(255, 255, 255, 0.035) 50%,
        transparent 50.05%),
      var(--black);
    color: var(--white);
  }

  /* =========================================================
BACKGROUND DETAIL
========================================================= */
  .about-section::before {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    background-image:
      linear-gradient(rgba(255, 255, 255, 0.018) 1px,
        transparent 1px),
      linear-gradient(90deg,
        rgba(255, 255, 255, 0.018) 1px,
        transparent 1px);
    background-size: 80px 80px;
    mask-image: linear-gradient(to bottom,
        black,
        transparent 75%);
  }

  /* =========================================================
INNER
========================================================= */
  .about-inner {
    position: relative;
    z-index: 1;
    width: min(var(--container),
        calc(100% - (var(--page-padding) * 2)));
    margin: 0 auto;
  }

  /* =========================================================
HEADER
========================================================= */
  .about-header {
    position: relative;
    display: grid;
    grid-template-columns: 150px 1fr;
    gap: 4rem;
    min-height: 540px;
    padding: 7rem 0 5rem;
    border-bottom: 1px solid var(--border);
  }

  /* Large background number */
  .about-header::after {
    content: '01';
    position: absolute;
    right: -0.05em;
    bottom: -0.22em;
    color: rgba(255, 255, 255, 0.025);
    font-size: clamp(14rem, 27vw, 28rem);
    font-weight: 800;
    line-height: 0.7;
    letter-spacing: -0.09em;
    pointer-events: none;
  }

  /* =========================================================
HEADING
========================================================= */
  .about-heading {
    position: relative;
    z-index: 2;
    align-self: center;
    display: flex;
    flex-direction: column;
    max-width: 980px;
    font-size: clamp(4rem, 8.5vw, 9rem);
    font-weight: 600;
    line-height: 0.82;
    letter-spacing: -0.075em;
    text-transform: uppercase;
  }

  .about-heading span {
    display: block;
  }

  .about-heading .muted {
    color: #45453f;
  }

  .about-heading span:nth-child(2) {
    color: var(--white);
  }

  .about-heading .accent {
    position: relative;
    width: fit-content;
    color: var(--green);
  }

  /* Small yellow marker */
  .about-heading .accent::after {
    content: '';
    position: absolute;
    right: -2rem;
    top: 50%;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: var(--yellow);
    transform: translateY(-50%);
  }

  /* =========================================================
INTRO AREA
========================================================= */
  .about-intro {
    display: grid;
    grid-template-columns: 150px 1fr;
    gap: 4rem;
    padding: 5rem 0;
    border-bottom: 1px solid var(--border);
  }

  .about-intro-mark {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 52px;
    height: 52px;
    border: 1px solid var(--border-light);
    border-radius: 50%;
    color: var(--green);
    background: rgba(57, 245, 154, 0.025);
  }

  .about-intro-mark::before,
  .about-intro-mark::after {
    content: '';
    position: absolute;
    background: var(--border-light);
  }

  .about-intro-mark::before {
    left: -15px;
    width: 10px;
    height: 1px;
  }

  .about-intro-mark::after {
    top: -15px;
    width: 1px;
    height: 10px;
  }

  .about-intro-content {
    max-width: 1000px;
  }

  /* Main statement */
  .about-intro .lead {
    max-width: 930px;
    margin: 0;
    color: var(--white);
    font-size: clamp(1.5rem, 2.8vw, 2.7rem);
    font-weight: 400;
    line-height: 1.18;
    letter-spacing: -0.035em;
  }

  /* Supporting copy */
  .intro-bottom {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 4rem;
    max-width: 820px;
    margin: 3.5rem 0 0 auto;
  }

  .intro-bottom p {
    margin: 0;
    color: var(--grey);
    font-size: 0.82rem;
    line-height: 1.8;
  }

  /* =========================================================
STATEMENT
========================================================= */
  .about-statement {
    position: relative;
    display: grid;
    grid-template-columns: 70px 1fr auto;
    gap: 2rem;
    align-items: center;
    padding: 7rem 0;
    border-bottom: 1px solid var(--border);
  }

  /* Green vertical line */
  .statement-line {
    position: relative;
    width: 1px;
    height: 180px;
    background: var(--green);
  }

  .statement-line::before,
  .statement-line::after {
    content: '';
    position: absolute;
    left: -3px;
    width: 7px;
    height: 7px;
    border: 1px solid var(--green);
    border-radius: 50%;
    background: var(--black);
  }

  .statement-line::before {
    top: 0;
  }

  .statement-line::after {
    bottom: 0;
  }

  .statement-label {
    display: block;
    margin-bottom: 1.5rem;
    color: var(--yellow);
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.2em;
  }

  .about-statement h3 {
    max-width: 850px;
    margin: 0;
    color: var(--white);
    font-size: clamp(2.5rem, 5vw, 5.5rem);
    font-weight: 400;
    line-height: 0.95;
    letter-spacing: -0.06em;
  }

  .about-statement h3 strong {
    color: var(--green);
    font-weight: 500;
  }

  .statement-arrow {
    align-self: end;
    margin-bottom: 0.5rem;
    color: var(--grey-dark);
  }

  /* =========================================================
BENEFITS
========================================================= */
  .about-benefits {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    margin-top: 0;
    border-left: 1px solid var(--border);
  }

  .benefit-card {
    position: relative;
    min-height: 310px;
    padding: 2rem;
    border-right: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    background: transparent;
    transition:
      background 0.3s ease,
      transform 0.3s ease;
  }

  /* Number */
  .benefit-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    margin-bottom: 6rem;
    color: var(--green);
  }

  .benefit-number {
    color: var(--grey-dark);
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.15em;
  }

  /* Icon */
  .benefit-top svg {
    transition:
      transform 0.3s ease,
      color 0.3s ease;
  }

  /* Hover */
  .benefit-card:hover {
    background: rgba(57, 245, 154, 0.025);
    transform: translateY(-3px);
  }

  .benefit-card:hover .benefit-top svg {
    color: var(--yellow);
    transform: translate(4px, -4px);
  }

  /* Card title */
  .benefit-content h3 {
    margin: 0 0 0.8rem;
    color: var(--white);
    font-size: 1.4rem;
    font-weight: 500;
    letter-spacing: -0.035em;
  }

  /* Card text */
  .benefit-content p {
    max-width: 330px;
    margin: 0;
    color: var(--grey);
    font-size: 0.78rem;
    line-height: 1.75;
  }

  /* Bottom green indicator */
  .benefit-card::after {
    content: '';
    position: absolute;
    left: 2rem;
    bottom: 0;
    width: 0;
    height: 2px;
    background: var(--green);
    transition: width 0.35s ease;
  }

  .benefit-card:hover::after {
    width: 55px;
  }

  /* =========================================================
CAPABILITIES
========================================================= */
  .about-capabilities {
    display: grid;
    grid-template-columns: 0.8fr 1.2fr;
    gap: 7rem;
    padding: 7rem 0;
    border-bottom: 1px solid var(--border);
  }

  .capabilities-heading {
    position: relative;
  }

  .capabilities-heading span {
    display: block;
    margin-bottom: 1.5rem;
    color: var(--yellow);
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.2em;
  }

  .capabilities-heading p {
    max-width: 380px;
    margin: 0;
    color: var(--white);
    font-size: clamp(1.3rem, 2vw, 1.8rem);
    line-height: 1.2;
    letter-spacing: -0.035em;
  }

  /* List */
  .capabilities-list {
    border-top: 1px solid var(--border);
  }

  .capability-item {
    display: grid;
    grid-template-columns: 50px 1fr auto;
    align-items: center;
    min-height: 68px;
    border-bottom: 1px solid var(--border);
    transition:
      padding 0.25s ease,
      background 0.25s ease;
  }

  .capability-item:hover {
    padding-left: 0.75rem;
    background: rgba(255, 255, 255, 0.018);
  }

  .capability-number {
    color: var(--grey-dark);
    font-size: 0.6rem;
    font-weight: 700;
  }

  .capability-name {
    color: var(--white);
    font-size: 0.82rem;
  }

  .capability-item svg {
    color: var(--green);
    opacity: 0;
    transform: translateX(-8px);
    transition:
      opacity 0.25s ease,
      transform 0.25s ease;
  }

  .capability-item:hover svg {
    opacity: 1;
    transform: translateX(0);
  }

  /* =========================================================
BOTTOM CTA
========================================================= */
  .about-bottom {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 3rem;
    padding: 7rem 0 3rem;
  }

  .bottom-copy > span {
    display: block;
    margin-bottom: 1.25rem;
    color: var(--grey-dark);
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.2em;
  }

  .bottom-copy h3 {
    margin: 0;
    color: var(--white);
    font-size: clamp(3rem, 6vw, 6.5rem);
    font-weight: 500;
    line-height: 0.85;
    letter-spacing: -0.065em;
  }

  .about-cta {
    position: relative;
    display: inline-flex;
    align-items: center;
    justify-content: space-between;
    min-width: 210px;
    padding: 1rem 1.15rem;
    border: 1px solid var(--green);
    color: var(--black);
    background: var(--green);
    font-size: 0.7rem;
    font-weight: 700;
    text-decoration: none;
    letter-spacing: 0.06em;
    overflow: hidden;
    transition:
      color 0.3s ease,
      background 0.3s ease;
  }

  .about-cta::before {
    content: '';
    position: absolute;
    inset: 0;
    background: var(--black);
    transform: translateY(100%);
    transition: transform 0.3s ease;
  }

  .about-cta span,
  .about-cta svg {
    position: relative;
    z-index: 1;
  }

  .about-cta:hover {
    color: var(--green);
  }

  .about-cta:hover::before {
    transform: translateY(0);
  }

  .about-cta:hover svg {
    transform: translate(3px, -3px);
  }

  /* =========================================================
TABLET
========================================================= */
  @media (max-width: 900px) {
    .about-header {
      grid-template-columns: 100px 1fr;
      gap: 2rem;
      min-height: 430px;
      padding-top: 5rem;
    }

    .about-heading {
      font-size: clamp(3.5rem, 9vw, 6rem);
    }

    .about-intro {
      grid-template-columns: 100px 1fr;
      gap: 2rem;
    }

    .about-statement {
      grid-template-columns: 45px 1fr auto;
    }

    .about-benefits {
      grid-template-columns: 1fr;
    }

    .benefit-card {
      min-height: 240px;
    }

    .benefit-top {
      margin-bottom: 4rem;
    }

    .about-capabilities {
      grid-template-columns: 1fr;
      gap: 3rem;
    }
  }

  /* =========================================================
MOBILE
========================================================= */
  @media (max-width: 650px) {
    .about-section {
      background:
        linear-gradient(90deg,
          transparent 49.8%,
          rgba(255, 255, 255, 0.025) 50%,
          transparent 50.2%),
        var(--black);
    }

    .about-header {
      display: block;
      min-height: auto;
      padding: 4rem 0 4rem;
    }

    .about-header::after {
      font-size: 11rem;
      right: -0.1em;
      bottom: -0.05em;
    }

    .about-heading {
      margin-top: 3rem;
      font-size: clamp(3.1rem, 14vw, 5rem);
      line-height: 0.86;
    }

    .about-heading .accent::after {
      right: -1rem;
      width: 7px;
      height: 7px;
    }

    .about-intro {
      display: block;
      padding: 3.5rem 0;
    }

    .about-intro-mark {
      margin-bottom: 2rem;
    }

    .about-intro .lead {
      font-size: 1.3rem;
      line-height: 1.3;
    }

    .intro-bottom {
      grid-template-columns: 1fr;
      gap: 1.25rem;
      margin-top: 2rem;
    }

    .about-statement {
      grid-template-columns: 3px 1fr;
      gap: 1.25rem;
      padding: 4.5rem 0;
    }

    .statement-line {
      height: 150px;
    }

    .about-statement h3 {
      font-size: clamp(2.2rem, 10vw, 3.4rem);
    }

    .statement-arrow {
      display: none;
    }

    .benefit-card {
      min-height: 220px;
      padding: 1.5rem;
    }

    .benefit-top {
      margin-bottom: 3.5rem;
    }

    .about-capabilities {
      padding: 4.5rem 0;
      gap: 2.5rem;
    }

    .capabilities-heading p {
      font-size: 1.25rem;
    }

    .capability-item {
      grid-template-columns: 35px 1fr auto;
      min-height: 60px;
    }

    .capability-item svg {
      opacity: 1;
      transform: none;
    }

    .about-bottom {
      display: block;
      padding: 4.5rem 0 2rem;
    }

    .bottom-copy h3 {
      font-size: clamp(3rem, 13vw, 5rem);
    }

    .about-cta {
      width: 100%;
      margin-top: 2.5rem;
    }
  }

  /* =========================================================
SMALL MOBILE
========================================================= */
  @media (max-width: 400px) {
    .about-heading {
      font-size: 2.9rem;
    }

    .about-intro .lead {
      font-size: 1.15rem;
    }

    .benefit-card {
      min-height: 205px;
    }

    .capability-name {
      font-size: 0.75rem;
    }
  }
</style>