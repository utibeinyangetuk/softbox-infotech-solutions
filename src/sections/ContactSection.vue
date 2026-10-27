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
				<SectionLabel number="04" title="Contact" accent="blue" />
				<div class="intro-content">
					<div class="intro-heading">
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
				<div class="detail">
					<div class="detail-label">
						<Phone :size="17" />
						<span>PHONE</span>
					</div>
					<div class="phone-numbers">
						<a href="tel:08026754712">080 2675 4712</a>
						<a href="tel:07031093053">070 3109 3053</a>
					</div>
				</div>
				<div class="detail">
					<div class="detail-label">
						<MapPin :size="17" />
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
			<!-- SIMPLE CTA -->
			<div class="contact-cta">
				<div>
					<span>READY TO START?</span>
					<h3>Start a conversation.</h3>
				</div>
				<a href="tel:08026754712">
					Call Softbox
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
	padding: 5rem var(--page-padding);
}
/* INTRO */
.contact-intro {
	display: grid;
	grid-template-columns: 160px 1fr;
	gap: 3rem;
	padding-bottom: 3.5rem;
	border-bottom: 1px solid var(--border);
}
.intro-content {
	display: grid;
	grid-template-columns: minmax(0, 1.5fr) minmax(240px, 0.5fr);
	gap: 4rem;
	align-items: end;
}
.intro-heading h2 {
	margin: 0;
	font-size: clamp(3rem, 5.2vw, 5.8rem);
	line-height: 0.98;
	letter-spacing: -0.055em;
	font-weight: 700;
}
.intro-heading h2 span {
	display: block;
	color: var(--accent);
}
.intro-copy {
	padding-bottom: 0.35rem;
}
.intro-copy p {
	margin: 0;
	color: var(--text-secondary);
	font-size: 1rem;
	line-height: 1.65;
}
/* DETAILS */
.contact-details {
	display: grid;
	grid-template-columns: 1fr 1fr;
	border-bottom: 1px solid var(--border);
}
.detail {
	padding: 3rem 0;
}
.detail + .detail {
	padding-left: 3rem;
	border-left: 1px solid var(--border);
}
.detail-label {
	display: flex;
	align-items: center;
	gap: 0.6rem;
	margin-bottom: 1.25rem;
	color: var(--text-muted);
	font-size: 0.7rem;
	font-weight: 700;
	letter-spacing: 0.13em;
}
.detail-label svg {
	color: var(--accent);
}
.phone-numbers {
	display: flex;
	flex-direction: column;
	gap: 0.35rem;
}
.phone-numbers a {
	color: var(--text);
	font-size: clamp(1.7rem, 3vw, 2.8rem);
	line-height: 1.05;
	font-weight: 600;
	letter-spacing: -0.04em;
	text-decoration: none;
}
.phone-numbers a:hover {
	color: var(--accent);
}
address {
	color: var(--text);
	font-size: 1.2rem;
	font-style: normal;
	line-height: 1.5;
}
.map-link {
	display: inline-flex;
	align-items: center;
	gap: 0.4rem;
	margin-top: 1.25rem;
	color: var(--accent);
	font-size: 0.75rem;
	font-weight: 650;
	text-transform: uppercase;
	letter-spacing: 0.05em;
	text-decoration: none;
}
.map-link:hover {
	color: var(--accent-dark);
}
/* CTA */
.contact-cta {
	display: flex;
	align-items: center;
	justify-content: space-between;
	gap: 2rem;
	padding: 3rem 0;
}
.contact-cta span {
	color: var(--text-muted);
	font-size: 0.68rem;
	font-weight: 700;
	letter-spacing: 0.13em;
}
.contact-cta h3 {
	margin: 0.45rem 0 0;
	font-size: clamp(1.8rem, 3vw, 3rem);
	line-height: 1;
	letter-spacing: -0.04em;
}
.contact-cta a {
	display: inline-flex;
	align-items: center;
	gap: 0.6rem;
	padding: 0.9rem 1.1rem;
	background: var(--accent);
	color: var(--text-inverse);
	font-size: 0.75rem;
	font-weight: 650;
	text-transform: uppercase;
	text-decoration: none;
}
.contact-cta a:hover {
	background: var(--accent-dark);
}
/* MOBILE */
@media (max-width: 700px) {
	.contact-container {
		padding-top: 4rem;
		padding-bottom: 3rem;
	}
	.contact-intro {
		grid-template-columns: 1fr;
		gap: 2rem;
	}
	.intro-content {
		grid-template-columns: 1fr;
		gap: 1.25rem;
	}
	.intro-heading h2 {
		font-size: clamp(2.8rem, 12vw, 4.5rem);
	}
	.contact-details {
		grid-template-columns: 1fr;
	}
	.detail {
		padding: 2rem 0;
	}
	.detail + .detail {
		padding-left: 0;
		border-left: 0;
		border-top: 1px solid var(--border);
	}
	.phone-numbers a {
		font-size: 1.8rem;
	}
	address {
		font-size: 1.05rem;
	}
	.contact-cta {
		align-items: flex-start;
		flex-direction: column;
		padding-top: 2.5rem;
	}
	.contact-cta a {
		width: 100%;
		justify-content: space-between;
	}
}
</style>
