<script setup>
  import {
    ArrowUpRight,
    Boxes,
    Calculator,
    PackageSearch,
    ShoppingBasket,
    UsersRound
  } from 'lucide-vue-next';

  import SectionLabel from '@/components/SectionLabel.vue';
  import SoftwarePlatforms from '@/components/SoftwarePlatforms.vue';

  const solutions = [
    {
      number: '01',
      name: 'Accounting Software',
      shortName: 'ACCOUNTING',
      icon: Calculator,
      description:
        'Manage finances, transactions and essential accounting processes with software built for clearer day-to-day business operations.'
    },

    {
      number: '02',
      name: 'Enterprise Resource Planning',
      shortName: 'ERP',
      icon: Boxes,
      description:
        'Connect key areas of your organisation through integrated ERP systems that bring business processes together.'
    },

    {
      number: '03',
      name: 'Inventory Software',
      shortName: 'INVENTORY',
      icon: PackageSearch,
      description:
        'Keep track of stock, movement and availability with inventory systems that give your business better visibility.'
    },

    {
      number: '04',
      name: 'Supermarket Software',
      shortName: 'RETAIL',
      icon: ShoppingBasket,
      description:
        'Streamline retail and point-of-sale operations with practical software for supermarkets and growing retail businesses.'
    },

    {
      number: '05',
      name: 'HR Software',
      shortName: 'HUMAN RESOURCES',
      icon: UsersRound,
      description:
        'Organise employee information and HR processes with digital tools that make people management easier.'
    }
  ]
</script>


<template>
  <section id="solutions" class="solutions site-section">

    <div class="section-inner">


      <!-- =================================================
           SECTION HEADER
      ================================================== -->

      <div class="solutions-header">

        <div class="solutions-index">

          <SectionLabel number="02" title="Business Management" />

          <span class="index-line"></span>

          <span class="index-meta">
            SOFTWARE / OPERATIONS / MANAGEMENT
          </span>

        </div>


        <div class="solutions-heading">

          <p class="heading-kicker">
            BUSINESS SYSTEMS
          </p>

          <h2>
            Technology
            <span>that works.</span>
          </h2>

          <div class="heading-bottom">

            <p class="intro">
              The right business software should do more than
              store information. It should help your people work
              better, give you greater visibility and make everyday
              decisions easier.
            </p>

            <div class="heading-mark">
              <span></span>
              <span></span>
              <span></span>
            </div>

          </div>

        </div>

      </div>


      <!-- =================================================
           SOLUTION LIST
      ================================================== -->

      <div class="solution-list">

        <article v-for="solution in solutions" :key="solution.number" class="solution-item">

          <!-- Number -->

          <div class="solution-number">
            {{ solution.number }}
          </div>


          <!-- Main content -->

          <div class="solution-main">

            <div class="solution-title-row">

              <div class="solution-title">

                <span class="solution-category">
                  {{ solution.shortName }}
                </span>

                <h3>
                  {{ solution.name }}
                </h3>

              </div>

              <component :is="solution.icon" class="solution-icon" :size="32" :stroke-width="1.1" />

            </div>


            <div class="solution-bottom">

              <p>
                {{ solution.description }}
              </p>

              <span class="solution-link">
                EXPLORE
                <ArrowUpRight :size="17" :stroke-width="1.3" />
              </span>

            </div>

          </div>

        </article>

      </div>


      <!-- =================================================
           PLATFORM AREA
      ================================================== -->

      <div class="platform-area">

        <div class="platform-header">

          <div>

            <span class="platform-number">
              02 / 01
            </span>

            <h3>
              Platforms we
              <span>work with.</span>
            </h3>

          </div>

          <p>
            We help businesses select and implement
            technology that fits their operations,
            requirements and growth.
          </p>

        </div>


        <div class="platform-frame">
          <SoftwarePlatforms />
        </div>

      </div>


      <!-- =================================================
           BOTTOM STATEMENT
      ================================================== -->

      <div class="solutions-footer">

        <div class="footer-line"></div>

        <p>
          Good software is not about having more tools.
          <strong>It is about having the right ones.</strong>
        </p>

        <ArrowUpRight :size="30" :stroke-width="1.2" />

      </div>

    </div>

  </section>
</template>


<style scoped>

  /* =========================================================
   SECTION
========================================================= */
  .solutions {
    position: relative;
    overflow: hidden;
    background:
      linear-gradient(90deg,
        transparent 49.95%,
        rgba(255, 255, 255, 0.03) 50%,
        transparent 50.05%),
      var(--black-soft);
  }

  /* Technical grid */
  .solutions::before {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    background-image:
      linear-gradient(rgba(255, 255, 255, 0.016) 1px,
        transparent 1px),
      linear-gradient(90deg,
        rgba(255, 255, 255, 0.016) 1px,
        transparent 1px);
    background-size: 80px 80px;
    mask-image: linear-gradient(to bottom,
        black,
        transparent 85%);
  }

  .section-inner {
    position: relative;
    z-index: 1;
  }

  /* =========================================================
   HEADER
========================================================= */
  .solutions-header {
    display: grid;
    grid-template-columns: 150px minmax(0, 1fr);
    gap: 4rem;
    min-height: 520px;
    padding: 7rem 0 5rem;
    border-bottom: 1px solid var(--border);
  }

  /* Left column */
  .solutions-index {
    display: flex;
    flex-direction: column;
    min-height: 330px;
  }

  .index-line {
    width: 1px;
    flex: 1;
    margin: 2rem 0;
    background: var(--border-light);
  }

  .index-meta {
    color: var(--grey-dark);
    font-size: 0.58rem;
    font-weight: 700;
    line-height: 1.5;
    letter-spacing: 0.14em;
    writing-mode: vertical-rl;
    transform: rotate(180deg);
  }

  /* Main heading */
  .solutions-heading {
    position: relative;
    align-self: center;
  }

  .heading-kicker {
    margin: 0 0 1.5rem;
    color: var(--yellow);
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.2em;
  }

  .solutions-heading h2 {
    position: relative;
    max-width: 950px;
    margin: 0;
    color: var(--white);
    font-size: clamp(4rem, 8.5vw, 9rem);
    font-weight: 600;
    line-height: 0.82;
    letter-spacing: -0.075em;
    text-transform: uppercase;
  }

  .solutions-heading h2::after {
    content: '02';
    position: absolute;
    right: 0;
    top: -0.45em;
    color: rgba(255, 255, 255, 0.025);
    font-size: clamp(13rem, 25vw, 25rem);
    font-weight: 800;
    line-height: 1;
    pointer-events: none;
  }

  .solutions-heading h2 span {
    display: block;
    color: var(--green);
  }

  /* Header bottom */
  .heading-bottom {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 3rem;
    margin-top: 3.5rem;
  }

  .intro {
    max-width: 560px;
    margin: 0;
    color: var(--grey);
    font-size: 0.85rem;
    line-height: 1.8;
  }

  /* Technical marker */
  .heading-mark {
    display: flex;
    align-items: flex-end;
    gap: 4px;
    height: 35px;
  }

  .heading-mark span {
    display: block;
    width: 2px;
    background: var(--green);
  }

  .heading-mark span:nth-child(1) {
    height: 12px;
  }

  .heading-mark span:nth-child(2) {
    height: 25px;
  }

  .heading-mark span:nth-child(3) {
    height: 35px;
    background: var(--yellow);
  }

  /* =========================================================
   SOLUTION LIST
========================================================= */
  .solution-list {
    border-left: 1px solid var(--border);
  }

  .solution-item {
    display: grid;
    grid-template-columns: 100px 1fr;
    min-height: 230px;
    border-bottom: 1px solid var(--border);
    transition:
      background 0.35s ease,
      padding 0.35s ease;
  }

  /* Number */
  .solution-number {
    display: flex;
    align-items: flex-start;
    padding: 2rem 1.5rem;
    border-right: 1px solid var(--border);
    color: var(--grey-dark);
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.12em;
  }

  /* Main */
  .solution-main {
    padding: 2rem 2.5rem;
  }

  /* Hover */
  .solution-item:hover {
    background: rgba(57, 245, 154, 0.025);
  }

  .solution-item:hover .solution-number {
    color: var(--green);
  }

  /* Title */
  .solution-title-row {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 2rem;
  }

  .solution-category {
    display: block;
    margin-bottom: 0.7rem;
    color: var(--yellow);
    font-size: 0.56rem;
    font-weight: 700;
    letter-spacing: 0.18em;
  }

  .solution-title h3 {
    max-width: 700px;
    margin: 0;
    color: var(--white);
    font-size: clamp(1.7rem, 3vw, 3rem);
    font-weight: 400;
    line-height: 1;
    letter-spacing: -0.045em;
  }

  .solution-icon {
    flex-shrink: 0;
    color: var(--green);
    transition:
      color 0.3s ease,
      transform 0.3s ease;
  }

  .solution-item:hover .solution-icon {
    color: var(--yellow);
    transform: translate(5px, -5px);
  }

  /* Bottom */
  .solution-bottom {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 2rem;
    margin-top: 3.5rem;
  }

  .solution-bottom p {
    max-width: 620px;
    margin: 0;
    color: var(--grey);
    font-size: 0.78rem;
    line-height: 1.7;
  }

  /* Explore */
  .solution-link {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    color: var(--grey-dark);
    font-size: 0.58rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    transition: color 0.25s ease;
  }

  .solution-item:hover .solution-link {
    color: var(--green);
  }

  /* =========================================================
   PLATFORMS
========================================================= */
  .platform-area {
    padding: 7rem 0 0;
  }

  .platform-header {
    display: grid;
    grid-template-columns: 1fr 0.8fr;
    gap: 5rem;
    align-items: end;
    padding-bottom: 3rem;
  }

  .platform-number {
    display: block;
    margin-bottom: 1.25rem;
    color: var(--yellow);
    font-size: 0.58rem;
    font-weight: 700;
    letter-spacing: 0.16em;
  }

  .platform-header h3 {
    margin: 0;
    color: var(--white);
    font-size: clamp(2.8rem, 5vw, 5.5rem);
    font-weight: 400;
    line-height: 0.9;
    letter-spacing: -0.06em;
  }

  .platform-header h3 span {
    color: var(--green);
  }

  .platform-header > p {
    max-width: 400px;
    margin: 0 0 0 auto;
    color: var(--grey);
    font-size: 0.78rem;
    line-height: 1.75;
  }

  /* Platform frame */
  .platform-frame {
    position: relative;
    padding: 2rem 0;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }

  /*
  The existing SoftwarePlatforms component is kept,
  but visually framed as part of the technical system.
*/
  .platform-frame :deep(.software-platforms) {
    background: transparent;
  }

  /* =========================================================
   FOOTER STATEMENT
========================================================= */
  .solutions-footer {
    display: grid;
    grid-template-columns: 50px 1fr auto;
    align-items: center;
    gap: 2rem;
    padding: 5rem 0 2rem;
  }

  .footer-line {
    width: 1px;
    height: 100px;
    background: var(--green);
  }

  .solutions-footer p {
    max-width: 650px;
    margin: 0;
    color: var(--grey);
    font-size: clamp(1.2rem, 2vw, 1.7rem);
    line-height: 1.25;
    letter-spacing: -0.025em;
  }

  .solutions-footer strong {
    color: var(--white);
    font-weight: 400;
  }

  .solutions-footer svg {
    color: var(--grey-dark);
  }

  /* =========================================================
   TABLET
========================================================= */
  @media (max-width: 900px) {
    .solutions-header {
      grid-template-columns: 100px 1fr;
      gap: 2rem;
      min-height: 450px;
    }

    .solutions-heading h2 {
      font-size: clamp(3.5rem, 9vw, 6rem);
    }

    .solution-item {
      grid-template-columns: 75px 1fr;
    }

    .solution-main {
      padding: 2rem;
    }

    .platform-header {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .platform-header > p {
      margin: 0;
    }
  }

  /* =========================================================
   MOBILE
========================================================= */
  @media (max-width: 650px) {
    .solutions-header {
      display: block;
      min-height: auto;
      padding: 4rem 0;
    }

    .solutions-index {
      display: block;
      min-height: auto;
    }

    .index-line {
      display: none;
    }

    .index-meta {
      display: block;
      margin-top: 1.5rem;
      writing-mode: horizontal-tb;
      transform: none;
    }

    .solutions-heading {
      margin-top: 4rem;
    }

    .heading-kicker {
      margin-bottom: 1.25rem;
    }

    .solutions-heading h2 {
      font-size: clamp(3.2rem, 14vw, 5rem);
    }

    .solutions-heading h2::after {
      font-size: 10rem;
      right: -0.1em;
      top: -0.2em;
    }

    .heading-bottom {
      display: block;
      margin-top: 2.5rem;
    }

    .heading-mark {
      margin-top: 2rem;
    }

    /* Solution list */
    .solution-item {
      grid-template-columns: 45px 1fr;
      min-height: auto;
    }

    .solution-number {
      padding: 1.5rem 0.8rem;
    }

    .solution-main {
      padding: 1.5rem;
    }

    .solution-title-row {
      gap: 1rem;
    }

    .solution-title h3 {
      font-size: 1.6rem;
      line-height: 1.05;
    }

    .solution-icon {
      width: 25px;
      height: 25px;
    }

    .solution-bottom {
      display: block;
      margin-top: 2rem;
    }

    .solution-link {
      margin-top: 1.25rem;
    }

    /* Platforms */
    .platform-area {
      padding-top: 5rem;
    }

    .platform-header {
      display: block;
    }

    .platform-header h3 {
      font-size: clamp(2.7rem, 11vw, 4rem);
    }

    .platform-header > p {
      margin-top: 1.75rem;
    }

    /* Footer */
    .solutions-footer {
      grid-template-columns: 3px 1fr;
      gap: 1.25rem;
      padding-top: 4rem;
    }

    .footer-line {
      height: 120px;
    }

    .solutions-footer svg {
      display: none;
    }
  }

  /* =========================================================
 SMALL MOBILE
========================================================= */
  @media (max-width: 400px) {
    .solutions-heading h2 {
      font-size: 2.9rem;
    }

    .solution-title h3 {
      font-size: 1.45rem;
    }

    .solution-main {
      padding: 1.25rem;
    }

    .solution-bottom p {
      font-size: 0.74rem;
    }
  }
</style>