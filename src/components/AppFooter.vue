<script setup>
import softboxLogo from '@/assets/images/softbox-logo.png';
import { ArrowUp, ArrowUpRight, Mail, MapPin, Phone } from 'lucide-vue-next';
const scrollToTop = () => {
	window.scrollTo({
		top: 0,
		behavior: 'smooth',
	});
};
</script>
<template>
	<footer class="site-footer">
		<div class="footer-grid"></div>
		<div class="footer-accent"></div>
		<div class="footer-inner">
			<!-- Main footer -->
			<div class="footer-main">
				<!-- Brand -->
				<div class="footer-brand">
					<img :src="softboxLogo" alt="Softbox Infotech Solutions Ltd" class="footer-logo" />
					<p class="footer-description">Business technology solutions that help organisations choose the right systems, work smarter and grow.</p>
					<a href="#contact" class="footer-cta">
						<span>START A CONVERSATION</span>
						<ArrowUpRight :size="18" :stroke-width="1.5" />
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
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#about">
						<span>About</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#solutions">
						<span>Solutions</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#services">
						<span>Services</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#contact">
						<span>Contact</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
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
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#solutions">
						<span>ERP</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#solutions">
						<span>Inventory Software</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#solutions">
						<span>Supermarket Software</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
					<a href="#solutions">
						<span>HR Software</span>
						<ArrowUpRight :size="15" :stroke-width="1.4" />
					</a>
				</div>
				<!-- Contact -->
				<div class="footer-column contact-column">
					<span class="footer-label">
						<small>03</small>
						CONTACT
					</span>
					<a href="tel:+2348026754712" class="contact-link">
						<Phone :size="16" :stroke-width="1.4" />
						<span>0802 675 4712</span>
					</a>
					<a href="tel:+2347031093053" class="contact-link">
						<Phone :size="16" :stroke-width="1.4" />
						<span>0703 109 3053</span>
					</a>
					<a href="#contact" class="contact-link">
						<Mail :size="16" :stroke-width="1.4" />
						<span>Get in touch</span>
					</a>
				</div>
			</div>
			<!-- Location -->
			<a href="#contact" class="footer-location">
				<div class="location-icon">
					<MapPin :size="17" :stroke-width="1.4" />
				</div>
				<div class="location-content">
					<span>OUR LOCATION</span>
					<strong> No 14, Eugene Plaza, Woji Road, Rumuogba, Port Harcourt, Nigeria </strong>
				</div>
				<ArrowUpRight :size="18" :stroke-width="1.4" aria-hidden="true" />
			</a>
			<!-- Bottom -->
			<div class="footer-bottom">
				<span class="copyright">
					© {{ new Date().getFullYear() }}
					Softbox Infotech Solutions Ltd.
				</span>
				<span class="footer-mark"> PORT HARCOURT · NIGERIA </span>
				<button class="back-to-top" type="button" aria-label="Back to top" @click="scrollToTop">
					<span>BACK TO TOP</span>
					<ArrowUp :size="16" :stroke-width="1.4" />
				</button>
			</div>
		</div>
	</footer>
</template>
<style scoped>
/* ─────────────────────────────────────────
   FOOTER
───────────────────────────────────────── */
.site-footer {
	position: relative;
	background: var(--bg-dark);
	color: var(--text-inverse);
	overflow: hidden;
	border-top: 1px solid #25282e;
}
/* Technical background */
.footer-grid {
	position: absolute;
	inset: 0;
	pointer-events: none;
	opacity: 0.45;
	background: linear-gradient(90deg, transparent 0, transparent calc(50% - 0.5px), rgba(255, 255, 255, 0.035) calc(50% - 0.5px), rgba(255, 255, 255, 0.035) 50%, transparent 50%, transparent 100%), linear-gradient(rgba(255, 255, 255, 0.018) 1px, transparent 1px);
	background-size:
		100% 100%,
		100% 80px;
}
.footer-accent {
	position: absolute;
	top: 0;
	left: 0;
	width: clamp(120px, 25vw, 360px);
	height: 2px;
	background: var(--accent);
}
/* ─────────────────────────────────────────
   INNER
───────────────────────────────────────── */
.footer-inner {
	position: relative;
	z-index: 1;
	width: min(100%, var(--container));
	margin: 0 auto;
	padding: 4rem var(--page-padding) 1.5rem;
}
/* ─────────────────────────────────────────
   MAIN
───────────────────────────────────────── */
.footer-main {
	display: grid;
	grid-template-columns:
		minmax(280px, 1.8fr)
		repeat(3, minmax(140px, 1fr));
	gap: clamp(2rem, 4vw, 5rem);
	padding-bottom: 3.5rem;
	border-bottom: 1px solid #292c32;
}
/* ─────────────────────────────────────────
   BRAND
───────────────────────────────────────── */
.footer-brand {
	max-width: 430px;
}
.brand-meta {
	display: flex;
	flex-direction: column;
	gap: 0.25rem;
	margin-bottom: 1.25rem;
	color: #737983;
	font-size: 0.68rem;
	font-weight: 600;
	letter-spacing: 0.16em;
}
.brand-meta span:first-child {
	color: var(--accent);
}
.footer-logo {
	display: block;
	width: min(100%, 200px);
	height: auto;
	max-height: 110px;
	object-fit: contain;
	object-position: left center;
	margin: 0 0 1.5rem 0;
}
.footer-description {
	max-width: 390px;
	margin: 0;
	color: #b2b7bf;
	font-size: 1rem;
	line-height: 1.7;
}
.footer-cta {
	display: inline-flex;
	align-items: center;
	gap: 0.8rem;
	margin-top: 2rem;
	padding-bottom: 0.55rem;
	border-bottom: 1px solid var(--accent);
	color: var(--text-inverse);
	text-decoration: none;
	font-size: 0.78rem;
	font-weight: 600;
	letter-spacing: 0.1em;
	transition:
		color 180ms ease,
		gap 180ms ease;
}
.footer-cta svg {
	color: var(--accent);
}
.footer-cta:hover {
	gap: 1.15rem;
	color: var(--accent);
}
/* ─────────────────────────────────────────
   COLUMNS
───────────────────────────────────────── */
.footer-column {
	display: flex;
	flex-direction: column;
	align-items: flex-start;
}
.footer-label {
	display: flex;
	align-items: center;
	gap: 0.7rem;
	margin-bottom: 1.25rem;
	color: #737983;
	font-size: 0.72rem;
	font-weight: 600;
	letter-spacing: 0.12em;
}
.footer-label small {
	color: var(--accent);
	font-family: monospace;
	font-size: 0.72rem;
	font-weight: 600;
}
.footer-column > a {
	display: flex;
	align-items: center;
	justify-content: space-between;
	gap: 1rem;
	width: 100%;
	max-width: 220px;
	padding: 0.55rem 0;
	border-bottom: 1px solid transparent;
	color: #aeb3bb;
	text-decoration: none;
	font-size: 0.92rem;
	line-height: 1.4;
	transition:
		color 180ms ease,
		padding-left 180ms ease,
		border-color 180ms ease;
}
.footer-column > a svg {
	flex-shrink: 0;
	opacity: 0;
	color: var(--accent);
	transform: translate(-4px, 4px);
	transition:
		opacity 180ms ease,
		transform 180ms ease;
}
.footer-column > a:hover {
	padding-left: 0.35rem;
	color: var(--text-inverse);
	border-bottom-color: #292c32;
}
.footer-column > a:hover svg {
	opacity: 1;
	transform: translate(0, 0);
}
/* Contact links */
.contact-column .contact-link {
	justify-content: flex-start;
	gap: 0.7rem;
}
.contact-column .contact-link svg {
	opacity: 1;
	transform: none;
	color: var(--accent);
}
.contact-column .contact-link:hover svg {
	color: var(--text-inverse);
}
/* ─────────────────────────────────────────
   LOCATION
───────────────────────────────────────── */
.footer-location {
	display: grid;
	grid-template-columns: auto 1fr auto;
	align-items: center;
	gap: 1.2rem;
	padding: 1.75rem 0;
	border-bottom: 1px solid #292c32;
	color: #aeb3bb;
	text-decoration: none;
	transition: color 180ms ease;
}
.location-icon {
	display: grid;
	place-items: center;
	width: 38px;
	height: 38px;
	border: 1px solid #383c43;
	color: var(--accent);
}
.location-content {
	display: flex;
	flex-direction: column;
	gap: 0.4rem;
}
.location-content span {
	color: #737983;
	font-size: 0.7rem;
	font-weight: 600;
	letter-spacing: 0.13em;
}
.location-content strong {
	color: #d2d5da;
	font-size: 0.95rem;
	font-weight: 450;
	line-height: 1.5;
}
.footer-location > svg {
	color: var(--accent);
	transition: transform 180ms ease;
}
.footer-location:hover {
	color: var(--text-inverse);
}
.footer-location:hover > svg {
	transform: translate(3px, -3px);
}
/* ─────────────────────────────────────────
   BOTTOM
───────────────────────────────────────── */
.footer-bottom {
	display: grid;
	grid-template-columns: 1fr auto 1fr;
	align-items: center;
	gap: 1rem;
	padding-top: 1.25rem;
	color: #737983;
	font-size: 0.72rem;
	line-height: 1.5;
}
.footer-mark {
	color: #737983;
	font-size: 0.68rem;
	font-weight: 600;
	letter-spacing: 0.1em;
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
	color: #aeb3bb;
	cursor: pointer;
	font: inherit;
	font-size: 0.72rem;
	font-weight: 600;
	letter-spacing: 0.08em;
	transition: color 180ms ease;
}
.back-to-top svg {
	color: var(--accent);
	transition: transform 180ms ease;
}
.back-to-top:hover {
	color: var(--text-inverse);
}
.back-to-top:hover svg {
	transform: translateY(-3px);
}
/* ─────────────────────────────────────────
   TABLET
───────────────────────────────────────── */
@media (max-width: 950px) {
	.footer-main {
		grid-template-columns: 1.5fr 1fr 1fr;
		gap: 2.5rem;
	}
	.footer-brand {
		grid-column: 1 / -1;
		max-width: 560px;
	}
}
/* ─────────────────────────────────────────
   MOBILE
───────────────────────────────────────── */
@media (max-width: 640px) {
	.footer-inner {
		padding-top: 3rem;
	}
	.footer-main {
		grid-template-columns: 1fr 1fr;
		gap: 2.5rem 1.5rem;
		padding-bottom: 2.75rem;
	}
	.footer-brand {
		grid-column: 1 / -1;
	}
	.footer-logo {
		width: 100%;
		max-width: 300px;
		max-height: none;
	}
	.footer-description {
		font-size: 0.95rem;
	}
	.footer-column > a {
		font-size: 0.88rem;
	}
	.footer-location {
		grid-template-columns: auto 1fr;
		gap: 1rem;
	}
	.footer-location > svg {
		display: none;
	}
	.location-content strong {
		font-size: 0.9rem;
	}
	.footer-bottom {
		grid-template-columns: 1fr auto;
		gap: 1rem;
	}
	.footer-mark {
		display: none;
	}
	.back-to-top {
		grid-column: 2;
		grid-row: 1;
	}
}
/* ─────────────────────────────────────────
   SMALL MOBILE
───────────────────────────────────────── */
@media (max-width: 430px) {
	.footer-main {
		grid-template-columns: 1fr;
		gap: 0;
	}
	.footer-column {
		width: 100%;
		padding: 1.5rem 0;
		border-top: 1px solid #292c32;
	}
	.footer-column > a {
		max-width: 100%;
		font-size: 0.92rem;
	}
	.footer-description {
		font-size: 0.95rem;
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
