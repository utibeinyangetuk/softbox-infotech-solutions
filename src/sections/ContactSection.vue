<script setup>
  import {
    ArrowUpRight,
    MapPin,
    Phone
  } from 'lucide-vue-next';

  import AppFooter from '@/components/AppFooter.vue';
  import SectionLabel from '@/components/SectionLabel.vue';

  defineEmits(['go-to'])

  const mapUrl =
    'https://www.google.com/maps/place/Eugene+Plaza,+Obia,+Port+Harcourt+500102,+Rivers/@4.8400391,7.0414198,21z/data=!4m10!1m2!2m1!1sEugene+Plaza,+rumuogba!3m6!1s0x1069cd99a064515d:0x815a7c1a675ca802!8m2!3d4.8399712!4d7.0416527!15sChZFdWdlbmUgUGxhemEsIHJ1bXVvZ2JhkgERY29tcG91bmRfYnVpbGRpbmfigAQA!16s%2Fg%2F11jt1dkwkd'
</script>

<template>
  <section class="contact" id="contact">

    <!-- CONTACT MAIN -->
    <div class="contact-main site-section">

      <div class="section-inner">

        <!-- HEADER -->
        <div class="contact-header">

          <div class="header-label">
            <SectionLabel number="04" title="Contact" accent="yellow" />
          </div>

          <div class="header-main">

            <span class="technical-label">
              CONNECT / DISCUSS / BUILD
            </span>

            <h2>
              Let's find the
              <span>right solution.</span>
            </h2>

            <p class="intro">
              Tell us what your business needs and we'll help you identify
              the right technology, software or support to move things
              forward.
            </p>

          </div>

        </div>


        <!-- CONTACT DETAILS -->
        <div class="contact-grid">

          <!-- PHONE 01 -->
          <a class="contact-item" href="tel:+2348026754712">

            <div class="item-top">
              <span>01 / CALL</span>

              <Phone :size="18" :stroke-width="1.4" />
            </div>

            <div class="item-main">
              <strong>08026754712</strong>
              <span>Primary contact</span>
            </div>

            <ArrowUpRight class="item-arrow" :size="20" :stroke-width="1.4" />

          </a>


          <!-- PHONE 02 -->
          <a class="contact-item" href="tel:+2347031093053">

            <div class="item-top">
              <span>02 / CALL</span>

              <Phone :size="18" :stroke-width="1.4" />
            </div>

            <div class="item-main">
              <strong>07031093053</strong>
              <span>Alternative contact</span>
            </div>

            <ArrowUpRight class="item-arrow" :size="20" :stroke-width="1.4" />

          </a>


          <!-- ADDRESS -->
          <a class="contact-item address" :href="mapUrl" target="_blank" rel="noopener noreferrer">

            <div class="item-top">
              <span>03 / VISIT</span>

              <MapPin :size="18" :stroke-width="1.4" />
            </div>

            <div class="address-main">

              <div>
                <strong>
                  No. 14, Eugene Plaza,
                  <br />
                  Woji Road, Rumuogba,
                  <br />
                  Port Harcourt.
                </strong>

                <span>
                  Open location in Google Maps
                </span>
              </div>

              <div class="map-marker">
                <span></span>
                <small>PORT HARCOURT / NG</small>
              </div>

            </div>

            <ArrowUpRight class="item-arrow" :size="22" :stroke-width="1.4" />

          </a>

        </div>


        <!-- CONTACT STATEMENT -->
        <div class="contact-statement">

          <div class="statement-label">
            <span></span>
            <p>START A CONVERSATION</p>
          </div>

          <div class="statement-main">

            <h3>
              Good technology
              <span>starts with the right questions.</span>
            </h3>

            <p>
              Whether you're looking for accounting software, an ERP system,
              inventory management, training or ongoing support, we're ready
              to understand your requirements.
            </p>

          </div>

        </div>

      </div>

    </div>


    <!-- FOOTER -->
    <AppFooter />

  </section>
</template>


<style scoped>

  /* =====================================================
   CONTACT
===================================================== */
  .contact {
    position: relative;
    background: var(--black);
  }

  /* =====================================================
   HEADER
===================================================== */
  .contact-header {
    display: grid;
    grid-template-columns: 150px 1fr;
    gap: 2rem;
    min-height: 520px;
    border-bottom: 1px solid var(--border);
  }

  .header-label {
    padding-top: 2rem;
  }

  .header-main {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 4rem 0;
  }

  /* large background number */
  .header-main::before {
    content: '04';
    position: absolute;
    right: 0;
    top: 1rem;
    color: rgba(255, 255, 255, 0.025);
    font-size: clamp(9rem, 22vw, 20rem);
    font-weight: 700;
    line-height: 0.8;
    letter-spacing: -0.08em;
    pointer-events: none;
  }

  /* technical label */
  .technical-label {
    position: relative;
    z-index: 1;
    display: block;
    margin-bottom: 1.5rem;
    color: var(--green);
    font-size: 0.65rem;
    font-weight: 600;
    letter-spacing: 0.18em;
  }

  /* heading */
  .header-main h2 {
    position: relative;
    z-index: 1;
    max-width: 1000px;
    margin: 0;
    color: var(--white);
    font-size: clamp(4rem, 9vw, 9rem);
    font-weight: 500;
    line-height: 0.86;
    letter-spacing: -0.065em;
    text-transform: uppercase;
  }

  .header-main h2 span {
    display: block;
    color: var(--yellow);
  }

  /* intro */
  .intro {
    position: relative;
    z-index: 1;
    max-width: 570px;
    margin: 2.5rem 0 0;
    color: var(--grey);
    font-size: 0.95rem;
    line-height: 1.75;
  }

  /* =====================================================
   CONTACT GRID
===================================================== */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    border-bottom: 1px solid var(--border);
  }

  /* =====================================================
   CONTACT ITEM
===================================================== */
  .contact-item {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 270px;
    padding: 2rem;
    border-right: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    color: var(--white);
    text-decoration: none;
    transition:
      background 0.35s ease,
      color 0.35s ease,
      padding 0.35s ease;
  }

  .contact-item:nth-child(2) {
    border-right: 0;
  }

  .contact-item:hover {
    background: var(--green);
    color: var(--black);
    padding-left: 2.5rem;
  }

  /* top */
  .item-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: var(--green);
    font-size: 0.6rem;
    letter-spacing: 0.16em;
  }

  .contact-item:hover .item-top {
    color: var(--black);
  }

  /* main */
  .item-main {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .item-main strong {
    font-size: clamp(1.8rem, 4vw, 3.5rem);
    font-weight: 400;
    line-height: 0.95;
    letter-spacing: -0.045em;
  }

  .item-main span {
    color: var(--grey-dark);
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .contact-item:hover .item-main span {
    color: rgba(0, 0, 0, 0.6);
  }

  /* arrow */
  .item-arrow {
    position: absolute;
    right: 2rem;
    bottom: 2rem;
    color: var(--yellow);
    transition:
      transform 0.3s ease,
      color 0.3s ease;
  }

  .contact-item:hover .item-arrow {
    color: var(--black);
    transform: translate(5px, -5px);
  }

  /* =====================================================
   ADDRESS
===================================================== */
  .address {
    grid-column: 1 / -1;
    min-height: 350px;
    border-right: 0;
    border-top: 1px solid var(--yellow);
    border-bottom: 0;
  }

  .address:hover {
    background: var(--yellow);
  }

  /* address content */
  .address-main {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 3rem;
  }

  .address-main strong {
    display: block;
    max-width: 700px;
    font-size: clamp(2rem, 5vw, 4.5rem);
    font-weight: 400;
    line-height: 0.95;
    letter-spacing: -0.045em;
  }

  .address-main > div:first-child > span {
    display: block;
    margin-top: 1.5rem;
    color: var(--grey);
    font-size: 0.65rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  .address:hover .address-main > div:first-child > span {
    color: rgba(0, 0, 0, 0.6);
  }

  /* map marker */
  .map-marker {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 0.75rem;
    padding-right: 3rem;
  }

  .map-marker span {
    position: relative;
    display: block;
    width: 28px;
    height: 28px;
    border: 1px solid var(--yellow);
    border-radius: 50%;
  }

  .map-marker span::after {
    content: '';
    position: absolute;
    left: 50%;
    top: 50%;
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: var(--yellow);
    transform: translate(-50%, -50%);
  }

  .map-marker small {
    color: var(--grey-dark);
    font-size: 0.55rem;
    letter-spacing: 0.15em;
  }

  .address:hover .map-marker span {
    border-color: var(--black);
  }

  .address:hover .map-marker span::after {
    background: var(--black);
  }

  .address:hover .map-marker small {
    color: rgba(0, 0, 0, 0.6);
  }

  /* =====================================================
   CONTACT STATEMENT
===================================================== */
  .contact-statement {
    display: grid;
    grid-template-columns: 150px 1fr;
    gap: 2rem;
    padding: 7rem 0;
    border-bottom: 1px solid var(--border);
  }

  .statement-label {
    display: flex;
    align-items: flex-start;
    gap: 0.75rem;
    padding-top: 0.5rem;
  }

  .statement-label span {
    width: 28px;
    height: 1px;
    margin-top: 0.45rem;
    background: var(--green);
  }

  .statement-label p {
    margin: 0;
    color: var(--grey-dark);
    font-size: 0.6rem;
    letter-spacing: 0.15em;
  }

  .statement-main h3 {
    max-width: 950px;
    margin: 0;
    color: var(--white);
    font-size: clamp(3rem, 6vw, 6rem);
    font-weight: 400;
    line-height: 0.92;
    letter-spacing: -0.055em;
  }

  .statement-main h3 span {
    display: block;
    color: var(--green);
  }

  .statement-main p {
    max-width: 600px;
    margin: 2rem 0 0;
    color: var(--grey);
    font-size: 0.9rem;
    line-height: 1.7;
  }

  /* =====================================================
   TABLET
===================================================== */
  @media (max-width: 1000px) {
    .contact-header {
      grid-template-columns: 110px 1fr;
    }

    .contact-item {
      min-height: 240px;
    }

    .address-main {
      align-items: flex-start;
    }

    .map-marker {
      display: none;
    }
  }

  /* =====================================================
   MOBILE
===================================================== */
  @media (max-width: 700px) {
    .contact-header {
      grid-template-columns: 1fr;
      min-height: auto;
    }

    .header-label {
      padding-top: 1.5rem;
    }

    .header-main {
      padding: 3rem 0 4rem;
    }

    .header-main h2 {
      font-size: clamp(3.5rem, 16vw, 6rem);
    }

    .intro {
      max-width: 100%;
      margin-top: 2rem;
    }

    /* contact items */
    .contact-grid {
      grid-template-columns: 1fr;
    }

    .contact-item,
    .contact-item:nth-child(2) {
      min-height: 210px;
      border-right: 0;
    }

    .address {
      grid-column: auto;
      min-height: 280px;
    }

    .address-main {
      display: block;
    }

    .address-main strong {
      font-size: clamp(1.8rem, 9vw, 3rem);
    }

    /* statement */
    .contact-statement {
      grid-template-columns: 1fr;
      gap: 2rem;
      padding: 5rem 0;
    }

    .statement-main h3 {
      font-size: clamp(2.8rem, 13vw, 5rem);
    }
  }
</style>