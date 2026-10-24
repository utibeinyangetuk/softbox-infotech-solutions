<script setup>
  import { ArrowUpRight } from 'lucide-vue-next';

  import erpnextLogo from '@/assets/logos/erpnext.svg';
  import quickbooksLogo from '@/assets/logos/quickbooks.svg';
  import sageLogo from '@/assets/logos/sage.svg';
  import zohoLogo from '@/assets/logos/zoho-books.svg';

  const platforms = [
    {
      number: '01',
      name: 'Zoho Books',
      logo: zohoLogo,
      type: 'Cloud Accounting',
      url: 'https://www.zoho.com/books/'
    },
    {
      number: '02',
      name: 'QuickBooks Online',
      logo: quickbooksLogo,
      type: 'Cloud Accounting',
      url: 'https://quickbooks.intuit.com/'
    },
    {
      number: '03',
      name: 'Sage',
      logo: sageLogo,
      type: 'Business Management',
      url: 'https://www.sage.com/en-ng/'
    },
    {
      number: '04',
      name: 'ERPNext',
      logo: erpnextLogo,
      type: 'ERP Platform',
      url: 'https://erpnext.com/'
    }
  ]
</script>

<template>
  <section class="platforms">
    <div class="platform-heading">
      <div class="platform-meta">
        <span>02 / 01</span>
        <p>SOFTWARE PLATFORMS</p>
      </div>

      <div class="platform-title">
        <span class="platform-kicker">TECHNOLOGY ECOSYSTEM</span>
        <h2>Platforms we <span>know.</span></h2>
      </div>

      <p class="platform-intro">
        We work with established business platforms to help organisations
        choose, implement and get more value from the technology they use.
      </p>
    </div>

    <div class="platform-list">
      <a v-for="platform in platforms" :key="platform.name" :href="platform.url" target="_blank"
        rel="noopener noreferrer" class="platform-row">
        <span class="platform-number">
          {{ platform.number }}
        </span>

        <div class="platform-logo">
          <img :src="platform.logo" :alt="`${platform.name} logo`" />
        </div>

        <div class="platform-info">
          <span>{{ platform.type }}</span>
          <strong>{{ platform.name }}</strong>
        </div>

        <div class="platform-action">
          <span>VIEW</span>
          <ArrowUpRight :size="18" :stroke-width="1.5" />
        </div>
      </a>
    </div>

    <div class="platform-note">
      <span class="note-line"></span>

      <p>
        Not sure which platform is right for your business?
        <a href="#contact">We can help you evaluate your options.</a>
      </p>
    </div>
  </section>
</template>

<style scoped>
  .platforms {
    margin-top: 7rem;
    border-top: 1px solid var(--yellow);
  }

  /* =========================
   HEADER
========================= */
  .platform-heading {
    display: grid;
    grid-template-columns: 150px 1fr 0.65fr;
    gap: 2rem;
    padding: 2rem 0 3.5rem;
    border-bottom: 1px solid var(--border);
  }

  .platform-meta {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .platform-meta span {
    color: var(--yellow);
    font-size: 0.7rem;
    letter-spacing: 0.16em;
    font-weight: 600;
  }

  .platform-meta p,
  .platform-kicker {
    margin: 0;
    color: var(--grey);
    font-size: 0.65rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
  }

  .platform-title {
    position: relative;
  }

  .platform-kicker {
    display: block;
    margin-bottom: 0.8rem;
    color: var(--green);
  }

  .platform-title h2 {
    margin: 0;
    color: var(--white);
    font-size: clamp(2.8rem, 6vw, 6rem);
    line-height: 0.9;
    letter-spacing: -0.055em;
    text-transform: uppercase;
  }

  .platform-title h2 span {
    color: var(--green);
  }

  .platform-intro {
    align-self: end;
    max-width: 420px;
    margin: 0;
    color: var(--grey);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  /* =========================
   PLATFORM LIST
========================= */
  .platform-list {
    border-bottom: 1px solid var(--border);
  }

  .platform-row {
    position: relative;
    display: grid;
    grid-template-columns: 85px 260px 1fr 100px;
    align-items: center;
    min-height: 145px;
    border-bottom: 1px solid var(--border);
    color: inherit;
    text-decoration: none;
    transition:
      background 0.3s ease,
      padding 0.3s ease;
  }

  .platform-row:last-child {
    border-bottom: 0;
  }

  .platform-row::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    width: 2px;
    height: 0;
    background: var(--green);
    transition: height 0.3s ease;
  }

  .platform-row:hover {
    background: rgba(57, 245, 154, 0.035);
    padding-left: 1rem;
  }

  .platform-row:hover::before {
    height: 100%;
  }

  .platform-number {
    color: var(--grey-dark);
    font-size: 0.7rem;
    letter-spacing: 0.12em;
  }

  /* =========================
   LOGO
========================= */
  .platform-logo {
    display: flex;
    align-items: center;
    height: 70px;
  }

  .platform-logo img {
    display: block;
    max-width: 170px;
    max-height: 55px;
    width: auto;
    height: auto;
    object-fit: contain;
    object-position: left center;
    transition: transform 0.3s ease;
  }

  .platform-row:hover .platform-logo img {
    transform: translateX(6px);
  }

  /* =========================
   INFO
========================= */
  .platform-info {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .platform-info span {
    color: var(--grey-dark);
    font-size: 0.65rem;
    letter-spacing: 0.14em;
    text-transform: uppercase;
  }

  .platform-info strong {
    color: var(--white);
    font-size: clamp(1.1rem, 2vw, 1.5rem);
    font-weight: 500;
    letter-spacing: -0.02em;
  }

  /* =========================
   ACTION
========================= */
  .platform-action {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    gap: 0.5rem;
    color: var(--green);
    font-size: 0.65rem;
    letter-spacing: 0.15em;
  }

  .platform-action svg {
    transition: transform 0.3s ease;
  }

  .platform-row:hover .platform-action svg {
    transform: translate(4px, -4px);
  }

  /* =========================
   NOTE
========================= */
  .platform-note {
    display: flex;
    align-items: center;
    gap: 1rem;
    padding-top: 1.5rem;
  }

  .note-line {
    width: 35px;
    height: 1px;
    background: var(--yellow);
    flex-shrink: 0;
  }

  .platform-note p {
    margin: 0;
    color: var(--grey);
    font-size: 0.8rem;
  }

  .platform-note a {
    color: var(--white);
    text-decoration: none;
    border-bottom: 1px solid var(--green);
    transition: color 0.2s ease;
  }

  .platform-note a:hover {
    color: var(--green);
  }

  /* =========================
   TABLET
========================= */
  @media (max-width: 1000px) {
    .platform-heading {
      grid-template-columns: 110px 1fr;
    }

    .platform-intro {
      grid-column: 2;
      margin-top: 1rem;
    }

    .platform-row {
      grid-template-columns: 65px 200px 1fr 80px;
    }
  }

  /* =========================
   MOBILE
========================= */
  @media (max-width: 700px) {
    .platforms {
      margin-top: 5rem;
    }

    .platform-heading {
      grid-template-columns: 1fr;
      gap: 1.5rem;
      padding-bottom: 2.5rem;
    }

    .platform-intro {
      grid-column: auto;
      max-width: 100%;
    }

    .platform-title h2 {
      font-size: clamp(2.6rem, 14vw, 4.5rem);
    }

    .platform-row {
      grid-template-columns: 45px 1fr auto;
      min-height: 120px;
      gap: 1rem;
    }

    .platform-logo {
      height: 55px;
    }

    .platform-logo img {
      max-width: 135px;
      max-height: 45px;
    }

    .platform-info {
      display: none;
    }

    .platform-action {
      padding-right: 0.25rem;
    }

    .platform-action span {
      display: none;
    }

    .platform-note {
      align-items: flex-start;
    }

    .note-line {
      margin-top: 0.55rem;
    }
  }
</style>