<script setup>
import AppFooter from '@/components/AppFooter.vue';
import SectionLabel from '@/components/SectionLabel.vue';
import { ArrowUpRight, MapPin, Phone } from 'lucide-vue-next';

const mapUrl = 'https://www.google.com/maps/search/?api=1&query=Eugene+Plaza,+Obia,+Port+Harcourt+500102';
</script>

<template>
	<section id="contact" class="contact-section">
		<div class="contact-container">
			<!-- INTRO -->
			<div class="contact-intro">
				<div class="contact-label">
					<SectionLabel number="04" title="Contact" accent="blue" />
				</div>

				<div class="intro-content">
					<div class="intro-heading">
						<span class="heading-kicker">GET IN TOUCH</span>

						<h2>
							Let's talk about
							<span>your business.</span>
						</h2>
					</div>

					<div class="intro-copy">
						<p>Tell us what you need. We'll help you find the right technology, software, support or people for your business.</p>
					</div>
				</div>
			</div>

			<!-- CONTACT DETAILS -->
			<div class="contact-details">
				<!-- PHONE -->
				<div class="detail">
					<div class="detail-label">
						<Phone :size="17" :stroke-width="1.7" />
						<span>PHONE</span>
					</div>

					<div class="phone-numbers">
						<a href="tel:08026754712"> 080 2675 4712 </a>

						<a href="tel:07031093053"> 070 3109 3053 </a>
					</div>
				</div>

				<!-- ADDRESS -->
				<div class="detail">
					<div class="detail-label">
						<MapPin :size="17" :stroke-width="1.7" />
						<span>ADDRESS</span>
					</div>

					<address>
						No. 14, Eugene Plaza,<br />
						Woji Road, Rumuogba,<br />
						Port Harcourt, Nigeria.
					</address>

					<a :href="mapUrl" target="_blank" rel="noopener noreferrer" class="map-link">
						Open in Google Maps
						<ArrowUpRight :size="16" />
					</a>
				</div>
			</div>

			<!-- CTA -->
			<div class="contact-cta">
				<div>
					<span>READY TO START?</span>

					<h3>Start a conversation.</h3>
				</div>

				<a href="tel:08026754712">
					<span>Call Softbox</span>
					<ArrowUpRight :size="18" />
				</a>
			</div>
		</div>

		<AppFooter />
	</section>
</template>

<style scoped>
.contact-section {
	background: var(--bg);
	color: var(--text);
	border-top: 1px solid var(--border);
}

.contact-container {
	width: min(100%, var(--container));
	margin: 0 auto;
	padding: clamp(4rem, 6vw, 5.5rem) var(--page-padding) 0;
}

/* =========================
   INTRO
========================= */

.contact-intro {
	display: grid;
	grid-template-columns: 120px minmax(0, 1fr);
	gap: 2.5rem;
	padding-bottom: 3.5rem;
	border-bottom: 1px solid var(--border);
}

.contact-label {
	padding-top: 0.15rem;
}

.intro-content {
	display: grid;
	grid-template-columns: minmax(0, 1.5fr) minmax(220px, 0.5fr);
	gap: 3.5rem;
	align-items: end;
}

.intro-heading {
	max-width: 800px;
}

.heading-kicker {
	display: block;
	margin-bottom: 1rem;
	color: var(--text-muted);
	font-size: 0.62rem;
	font-weight: 650;
	letter-spacing: 0.14em;
}

.intro-heading h2 {
	margin: 0;
	font-size: clamp(2.8rem, 5vw, 5rem);
	line-height: 0.98;
	letter-spacing: -0.055em;
	font-weight: 650;
}

.intro-heading h2 span {
	display: block;
	color: var(--accent);
}

.intro-copy {
	padding-bottom: 0.2rem;
}

.intro-copy p {
	max-width: 360px;
	margin: 0;
	color: var(--text-secondary);
	font-size: 0.92rem;
	line-height: 1.7;
}

.contact-details {
	display: grid;
	grid-template-columns: 1fr 1fr;
	border-bottom: 1px solid var(--border);
}

.detail {
	min-height: 190px;
	padding: 2.5rem 0;
}

.detail + .detail {
	padding-left: 3rem;
	border-left: 1px solid var(--border);
}

.detail-label {
	display: flex;
	align-items: center;
	gap: 0.55rem;
	margin-bottom: 1.1rem;
	color: var(--text-muted);
	font-size: 0.62rem;
	font-weight: 700;
	letter-spacing: 0.13em;
}

.detail-label svg {
	color: var(--accent);
}

.phone-numbers {
	display: flex;
	flex-direction: column;
	gap: 0.3rem;
}

.phone-numbers a {
	width: fit-content;
	color: var(--text);
	font-size: clamp(1.65rem, 2.8vw, 2.6rem);
	line-height: 1.05;
	font-weight: 600;
	letter-spacing: -0.04em;
	text-decoration: none;
	transition: color 0.2s ease;
}

.phone-numbers a:hover {
	color: var(--accent);
}

address {
	color: var(--text);
	font-size: 1rem;
	font-style: normal;
	line-height: 1.55;
}

.map-link {
	display: inline-flex;
	align-items: center;
	gap: 0.4rem;
	margin-top: 1.1rem;
	color: var(--accent);
	font-size: 0.62rem;
	font-weight: 650;
	text-transform: uppercase;
	letter-spacing: 0.06em;
	text-decoration: none;
	transition: gap 0.2s ease;
}

.map-link:hover {
	gap: 0.65rem;
}

.contact-cta {
	display: flex;
	align-items: center;
	justify-content: space-between;
	gap: 2rem;
	padding: 3rem 0;
}

.contact-cta > div > span {
	display: block;
	margin-bottom: 0.65rem;
	color: var(--text-muted);
	font-size: 0.62rem;
	font-weight: 700;
	letter-spacing: 0.13em;
}

.contact-cta h3 {
	margin: 0;
	font-size: clamp(1.8rem, 3vw, 3rem);
	line-height: 1;
	letter-spacing: -0.04em;
	font-weight: 600;
}

.contact-cta a {
	display: inline-flex;
	align-items: center;
	gap: 0.7rem;
	padding: 0.9rem 1rem;
	border: 1px solid var(--accent);
	background: var(--accent);
	color: var(--text-inverse);
	font-size: 0.65rem;
	font-weight: 700;
	text-transform: uppercase;
	letter-spacing: 0.08em;
	text-decoration: none;
	transition:
		background 0.2s ease,
		border-color 0.2s ease;
}

.contact-cta a:hover {
	background: var(--accent-hover);
	border-color: var(--accent-hover);
}

@media (max-width: 800px) {
	.contact-container {
		padding-top: 4rem;
	}

	.contact-intro {
		grid-template-columns: 1fr;
		gap: 1.5rem;
	}

	.intro-content {
		grid-template-columns: 1fr;
		gap: 1.25rem;
	}

	.intro-copy {
		padding-bottom: 0;
	}

	.intro-copy p {
		max-width: 600px;
	}

	.contact-details {
		grid-template-columns: 1fr;
	}

	.detail {
		min-height: auto;
		padding: 2rem 0;
	}

	.detail + .detail {
		padding-left: 0;
		border-left: 0;
		border-top: 1px solid var(--border);
	}

	.contact-cta {
		align-items: flex-start;
		flex-direction: column;
		padding: 2.75rem 0 3rem;
	}

	.contact-cta a {
		width: 100%;
		justify-content: space-between;
	}
}

@media (max-width: 520px) {
	.contact-container {
		padding-top: 3.25rem;
	}

	.contact-intro {
		gap: 1.5rem;
		padding-bottom: 2.5rem;
	}

	.intro-heading h2 {
		font-size: clamp(2.4rem, 11vw, 3.4rem);
	}

	.intro-copy p {
		font-size: 0.9rem;
		line-height: 1.65;
	}

	.detail {
		padding: 1.8rem 0;
	}

	.phone-numbers a {
		font-size: 1.7rem;
	}

	address {
		font-size: 0.95rem;
	}

	.contact-cta {
		padding-top: 2.5rem;
	}

	.contact-cta h3 {
		font-size: 2.1rem;
	}
}
</style>
