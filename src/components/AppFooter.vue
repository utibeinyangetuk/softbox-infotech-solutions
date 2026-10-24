<script setup>
  import { ArrowUp, ArrowUpRight, Mail, MapPin, Phone } from 'lucide-vue-next';

  import softboxLogo from '@/assets/images/softbox-logo.png';

  const scrollToTop = () => {
    window.scrollTo({
      top: 0,
      behavior: 'smooth',
    });
  };
</script>

<template>
  <footer class="site-footer">
    <div class="footer-grid-line"></div>

    <div class="footer-inner">
      <!-- Footer header -->
      <div class="footer-header">
        <div class="footer-index">
          <span>05</span>
          <span>SOFTBOX / END</span>
        </div>

        <div class="footer-status">
          <span class="status-dot"></span>
          BUSINESS TECHNOLOGY
        </div>
      </div>

      <!-- Main footer -->
      <div class="footer-main">
        <!-- Brand -->
        <div class="footer-brand">
          <div class="brand-mark">
            <span>SOFTBOX</span>
            <span>INFOTECH SOLUTIONS LTD</span>
          </div>

          <img :src="softboxLogo" alt="Softbox Infotech Solutions Ltd" class="footer-logo" />

          <p class="footer-description">Business technology solutions that help organisations work smarter, operate
            better and grow.</p>

          <a href="#contact" class="footer-cta">
            <span>START A CONVERSATION</span>
            <ArrowUpRight :size="17" />
          </a>
        </div>

        <!-- Navigation -->
        <div class="footer-column">
          <span class="footer-label">
            <small>01</small>
            NAVIGATION
          </span>

          <a href="#home">
            <span>Home</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#about">
            <span>About</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#solutions">
            <span>Solutions</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#services">
            <span>Services</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#contact">
            <span>Contact</span>
            <ArrowUpRight :size="13" />
          </a>
        </div>

        <!-- Solutions -->
        <div class="footer-column">
          <span class="footer-label">
            <small>02</small>
            SOLUTIONS
          </span>

          <a href="#solutions">
            <span>Accounting Software</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#solutions">
            <span>ERP</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#solutions">
            <span>Inventory Software</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#solutions">
            <span>Supermarket Software</span>
            <ArrowUpRight :size="13" />
          </a>

          <a href="#solutions">
            <span>HR Software</span>
            <ArrowUpRight :size="13" />
          </a>
        </div>

        <!-- Contact -->
        <div class="footer-column contact-column">
          <span class="footer-label">
            <small>03</small>
            CONTACT
          </span>

          <a href="tel:+2348026754712" class="contact-link">
            <Phone :size="14" />
            <span>0802 675 4712</span>
          </a>

          <a href="tel:+2347031093053" class="contact-link">
            <Phone :size="14" />
            <span>0703 109 3053</span>
          </a>

          <a href="#contact" class="contact-link">
            <Mail :size="14" />
            <span>Get in touch</span>
          </a>
        </div>
      </div>

      <!-- Location -->
      <a href="#contact" class="footer-location">
        <div class="location-icon">
          <MapPin :size="15" />
        </div>

        <div class="location-content">
          <span>OUR LOCATION</span>
          <strong> No 14, Eugene Plaza, Woji Road, Rumuogba, Port Harcourt, Nigeria </strong>
        </div>

        <ArrowUpRight :size="17" />
      </a>

      <!-- Large statement -->
      <div class="footer-statement">
        <span>BUSINESS TECHNOLOGY.</span>
        <strong>BETTER.</strong>
      </div>

      <!-- Bottom -->
      <div class="footer-bottom">
        <span>
          © {{ new Date().getFullYear() }}
          Softbox Infotech Solutions Ltd.
        </span>

        <span class="footer-location-code"> PORT HARCOURT / NG </span>

        <button class="back-to-top" type="button" aria-label="Back to top" @click="scrollToTop">
          <span>BACK TO TOP</span>
          <ArrowUp :size="15" />
        </button>
      </div>
    </div>
  </footer>
</template>

<style scoped>
  .site-footer {
    position: relative;
    background: var(--black);
    color: var(--white);
    overflow: hidden;
    border-top: 1px solid var(--border-light);
  }

  /* Technical background */
  .site-footer::before {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    background: linear-gradient(90deg, transparent 0, transparent calc(50% - 0.5px), rgba(255, 255, 255, 0.035) calc(50% - 0.5px), rgba(255, 255, 255, 0.035) 50%, transparent 50%, transparent 100%), linear-gradient(rgba(255, 255, 255, 0.018) 1px, transparent 1px);
    background-size:
      100% 100%,
      100% 80px;
  }

  .footer-grid-line {
    position: absolute;
    top: 0;
    left: 0;
    width: 32%;
    height: 1px;
    background: var(--green);
  }

  /* Main wrapper */
  .footer-inner {
    position: relative;
    z-index: 1;
    width: min(100%, var(--container));
    margin: 0 auto;
    padding: 2rem var(--page-padding) 1.5rem;
  }

  /* Header */
  .footer-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-bottom: 1.25rem;
    border-bottom: 1px solid var(--border);
    font-size: 0.65rem;
    letter-spacing: 0.16em;
    font-weight: 700;
  }

  .footer-index {
    display: flex;
    align-items: center;
    gap: 1rem;
    color: var(--grey);
  }

  .footer-index span:first-child {
    color: var(--yellow);
    font-family: monospace;
  }

  .footer-status {
    display: flex;
    align-items: center;
    gap: 0.55rem;
    color: var(--grey);
  }

  .status-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--green);
    box-shadow: 0 0 12px rgba(57, 245, 154, 0.5);
  }

  /* Main */
  .footer-main {
    display: grid;
    grid-template-columns: minmax(260px, 1.8fr) repeat(3, minmax(130px, 1fr));
    gap: 4rem;
    padding: 4rem 0;
    border-bottom: 1px solid var(--border);
  }

  /* Brand */
  .footer-brand {
    max-width: 390px;
  }

  .brand-mark {
    display: flex;
    flex-direction: column;
    gap: 0.2rem;
    margin-bottom: 1.2rem;
    color: var(--grey-dark);
    font-size: 0.55rem;
    font-weight: 700;
    letter-spacing: 0.2em;
  }

  .brand-mark span:first-child {
    color: var(--green);
  }

  .footer-logo {
    display: block;
    width: min(100%, 270px);
    height: auto;
    max-height: 105px;
    object-fit: contain;
    object-position: left center;
    margin-bottom: 1.2rem;
  }

  .footer-description {
    max-width: 330px;
    margin: 0;
    color: var(--grey);
    font-size: 0.88rem;
    line-height: 1.7;
  }

  .footer-cta {
    display: inline-flex;
    align-items: center;
    gap: 0.8rem;
    margin-top: 1.7rem;
    padding-bottom: 0.45rem;
    border-bottom: 1px solid var(--green);
    color: var(--white);
    text-decoration: none;
    font-size: 0.65rem;
    font-weight: 800;
    letter-spacing: 0.12em;
    transition:
      color 0.25s ease,
      gap 0.25s ease;
  }

  .footer-cta svg {
    color: var(--green);
  }

  .footer-cta:hover {
    gap: 1.1rem;
    color: var(--green);
  }

  /* Columns */
  .footer-column {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .footer-label {
    display: flex;
    align-items: center;
    gap: 0.65rem;
    margin-bottom: 1.4rem;
    color: var(--grey-dark);
    font-size: 0.62rem;
    font-weight: 800;
    letter-spacing: 0.14em;
  }

  .footer-label small {
    color: var(--yellow);
    font-family: monospace;
    font-size: 0.62rem;
  }

  .footer-column > a {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    max-width: 180px;
    padding: 0.48rem 0;
    color: var(--grey);
    text-decoration: none;
    font-size: 0.78rem;
    line-height: 1.4;
    border-bottom: 1px solid transparent;
    transition:
      color 0.25s ease,
      padding-left 0.25s ease,
      border-color 0.25s ease;
  }

  .footer-column > a svg {
    opacity: 0;
    color: var(--green);
    transform: translate(-4px, 4px);
    transition:
      opacity 0.25s ease,
      transform 0.25s ease;
  }

  .footer-column > a:hover {
    padding-left: 0.3rem;
    color: var(--white);
    border-bottom-color: var(--border);
  }

  .footer-column > a:hover svg {
    opacity: 1;
    transform: translate(0, 0);
  }

  /* Contact links */
  .contact-column .contact-link {
    justify-content: flex-start;
    gap: 0.65rem;
  }

  .contact-column .contact-link svg {
    opacity: 1;
    transform: none;
    color: var(--green);
    flex-shrink: 0;
  }

  .contact-column .contact-link:hover svg {
    color: var(--yellow);
  }

  /* Location */
  .footer-location {
    display: grid;
    grid-template-columns: auto 1fr auto;
    align-items: center;
    gap: 1rem;
    padding: 1.5rem 0;
    color: var(--grey);
    text-decoration: none;
    border-bottom: 1px solid var(--border);
    transition: color 0.25s ease;
  }

  .location-icon {
    display: grid;
    place-items: center;
    width: 32px;
    height: 32px;
    border: 1px solid var(--border-light);
    color: var(--green);
  }

  .location-content {
    display: flex;
    flex-direction: column;
    gap: 0.3rem;
  }

  .location-content span {
    color: var(--grey-dark);
    font-size: 0.58rem;
    font-weight: 800;
    letter-spacing: 0.16em;
  }

  .location-content strong {
    color: var(--grey);
    font-size: 0.78rem;
    font-weight: 500;
  }

  .footer-location > svg {
    color: var(--yellow);
    transition: transform 0.25s ease;
  }

  .footer-location:hover {
    color: var(--white);
  }

  .footer-location:hover > svg {
    transform: translate(3px, -3px);
  }

  /* Statement */
  .footer-statement {
    display: flex;
    align-items: baseline;
    gap: 0.6rem;
    padding: 4rem 0 3rem;
    font-size: clamp(2.6rem, 7vw, 7.5rem);
    line-height: 0.85;
    letter-spacing: -0.055em;
    text-transform: uppercase;
  }

  .footer-statement span {
    color: var(--white);
    font-weight: 800;
  }

  .footer-statement strong {
    color: var(--green);
    font-weight: 800;
  }

  /* Bottom */
  .footer-bottom {
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    align-items: center;
    gap: 1rem;
    padding-top: 1.25rem;
    color: var(--grey-dark);
    font-size: 0.62rem;
    letter-spacing: 0.06em;
  }

  .footer-location-code {
    color: var(--grey);
    font-family: monospace;
    font-size: 0.58rem;
    letter-spacing: 0.15em;
  }

  .back-to-top {
    display: inline-flex;
    align-items: center;
    justify-content: flex-end;
    gap: 0.7rem;
    justify-self: end;
    padding: 0;
    border: 0;
    background: transparent;
    color: var(--grey);
    cursor: pointer;
    font: inherit;
    font-size: 0.62rem;
    letter-spacing: 0.1em;
    transition: color 0.25s ease;
  }

  .back-to-top svg {
    color: var(--green);
    transition: transform 0.25s ease;
  }

  .back-to-top:hover {
    color: var(--white);
  }

  .back-to-top:hover svg {
    transform: translateY(-3px);
  }

  /* Tablet */
  @media (max-width: 900px) {
    .footer-main {
      grid-template-columns: 1.5fr 1fr 1fr;
      gap: 2.5rem;
    }

    .footer-brand {
      grid-column: 1 / -1;
      max-width: 500px;
    }

    .footer-statement {
      flex-direction: column;
      gap: 0.2rem;
    }
  }

  /* Mobile */
  @media (max-width: 640px) {
    .footer-inner {
      padding-top: 1.5rem;
    }

    .footer-header {
      align-items: flex-start;
      gap: 1rem;
    }

    .footer-status {
      font-size: 0.55rem;
      text-align: right;
    }

    .footer-main {
      grid-template-columns: 1fr 1fr;
      gap: 2.5rem 1.5rem;
      padding: 3rem 0;
    }

    .footer-brand {
      grid-column: 1 / -1;
    }

    .footer-logo {
      width: 100%;
      max-width: 280px;
      height: auto;
      max-height: none;
    }

    .footer-description {
      font-size: 0.82rem;
    }

    .footer-column > a {
      font-size: 0.72rem;
    }

    .footer-location {
      grid-template-columns: auto 1fr auto;
    }

    .location-content strong {
      font-size: 0.72rem;
      line-height: 1.5;
    }

    .footer-statement {
      padding: 3rem 0 2.5rem;
      font-size: clamp(2.5rem, 14vw, 5rem);
    }

    .footer-bottom {
      grid-template-columns: 1fr auto;
      gap: 1rem;
    }

    .footer-location-code {
      display: none;
    }

    .back-to-top {
      grid-column: 2;
      grid-row: 1;
    }
  }

  @media (max-width: 430px) {
    .footer-main {
      grid-template-columns: 1fr;
    }

    .footer-column {
      width: 100%;
      padding-top: 1rem;
      border-top: 1px solid var(--border);
    }

    .footer-column > a {
      max-width: 100%;
    }

    .footer-statement {
      font-size: clamp(2.3rem, 16vw, 4rem);
    }

    .footer-bottom {
      grid-template-columns: 1fr;
    }

    .back-to-top {
      grid-column: auto;
      grid-row: auto;
      justify-self: start;
    }
  }
</style>