<script setup>
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
		<div class="footer-grid-line"></div>
		<div class="footer-inner">
			<!-- MAIN FOOTER -->
			<div class="footer-main">
				<!-- NAVIGATION -->
				<div class="footer-column">
					<span class="footer-label">
						<small>01</small>
						NAVIGATION
					</span>
					<a href="#home">
						<span>Home</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#about">
						<span>About</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#solutions">
						<span>Solutions</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#services">
						<span>Services</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#contact">
						<span>Contact</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
				</div>
				<!-- SOLUTIONS -->
				<div class="footer-column">
					<span class="footer-label">
						<small>02</small>
						SOLUTIONS
					</span>
					<a href="#solutions">
						<span>Accounting Software</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#solutions">
						<span>Enterprise Resource Planning</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#solutions">
						<span>Inventory Software</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#solutions">
						<span>Supermarket Software</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
					<a href="#solutions">
						<span>HR Software</span>
						<ArrowUpRight :size="13" :stroke-width="1.5" />
					</a>
				</div>
				<!-- CONTACT -->
				<div class="footer-column contact-column">
					<span class="footer-label">
						<small>03</small>
						CONTACT
					</span>
					<a href="tel:+2348026754712" class="contact-link">
						<Phone :size="14" :stroke-width="1.5" />
						<span>080 2675 4712</span>
					</a>
					<a href="tel:+2347031093053" class="contact-link">
						<Phone :size="14" :stroke-width="1.5" />
						<span>070 3109 3053</span>
					</a>
					<a href="#contact" class="contact-link">
						<Mail :size="14" :stroke-width="1.5" />
						<span>Get in touch</span>
					</a>
				</div>
			</div>
			<!-- LOCATION -->
			<a href="#contact" class="footer-location">
				<div class="location-icon">
					<MapPin :size="15" :stroke-width="1.5" />
				</div>
				<div class="location-content">
					<span>OUR LOCATION</span>
					<strong> No. 14, Eugene Plaza, Woji Road, Rumuogba, Port Harcourt, Nigeria </strong>
				</div>
				<ArrowUpRight class="location-arrow" :size="17" :stroke-width="1.5" />
			</a>
			<!-- BOTTOM -->
			<div class="footer-bottom">
				<span>
					© {{ new Date().getFullYear() }}
					Softbox Infotech Solutions Ltd.
				</span>
				<span class="footer-location-code"> PORT HARCOURT · NIGERIA </span>
				<button class="back-to-top" type="button" aria-label="Back to top" @click="scrollToTop">
					<span>BACK TO TOP</span>
					<ArrowUp :size="15" :stroke-width="1.5" />
				</button>
			</div>
		</div>
	</footer>
</template>

<style scoped>
/* =========================================================
   FOOTER
========================================================= */
.site-footer {
	position: relative;
	width: 100%;
	overflow: hidden;
	background: var(--bg-dark);
	color: var(--text);
	border-top: 1px solid var(--border);
}
/* =========================================================
   SUBTLE BACKGROUND
========================================================= */
.site-footer::before {
	content: '';
	position: absolute;
	inset: 0;
	pointer-events: none;
	background: linear-gradient(90deg, transparent 0, transparent calc(50% - 0.5px), rgba(255, 255, 255, 0.025) calc(50% - 0.5px), rgba(255, 255, 255, 0.025) 50%, transparent 50%, transparent 100%), linear-gradient(rgba(255, 255, 255, 0.012) 1px, transparent 1px);
	background-size:
		100% 100%,
		100% 80px;
}
.footer-grid-line {
	position: absolute;
	top: 0;
	left: 0;
	width: 30%;
	height: 1px;
	background: var(--accent);
	z-index: 2;
}
/* =========================================================
   INNER
========================================================= */
.footer-inner {
	position: relative;
	z-index: 1;
	width: min(100%, var(--container));
	margin: 0 auto;
	padding: 0 var(--page-padding);
}
/* =========================================================
   MAIN
========================================================= */
.footer-main {
	display: grid;
	grid-template-columns:
		1fr
		1.4fr
		0.9fr;
	gap: 3rem;
	padding: 3.25rem 0;
	border-bottom: 1px solid var(--border);
}
/* =========================================================
   COLUMNS
========================================================= */
.footer-column {
	display: flex;
	flex-direction: column;
	align-items: flex-start;
}
.footer-label {
	display: flex;
	align-items: center;
	gap: 0.6rem;
	margin-bottom: 1.1rem;
	color: var(--text-muted);
	font-size: 0.6rem;
	font-weight: 700;
	letter-spacing: 0.13em;
}
.footer-label small {
	color: var(--accent);
	font-family: monospace;
	font-size: 0.6rem;
}
/* =========================================================
   LINKS
========================================================= */
.footer-column > a {
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 100%;
	max-width: 280px;
	padding-block: 0.4rem;
	color: var(--text-secondary);
	font-size: 0.76rem;
	line-height: 1.4;
	text-decoration: none;
	transition:
		color 0.2s ease,
		padding-left 0.2s ease;
}
.footer-column > a svg {
	opacity: 0;
	color: var(--accent);
	transform: translate(-4px, 4px);
	transition:
		opacity 0.2s ease,
		transform 0.2s ease;
}
.footer-column > a:hover {
	padding-left: 0.25rem;
	color: var(--text);
}
.footer-column > a:hover svg {
	opacity: 1;
	transform: translate(0, 0);
}
/* =========================================================
   CONTACT LINKS
========================================================= */
.contact-column .contact-link {
	justify-content: flex-start;
	gap: 0.6rem;
}
.contact-column .contact-link svg {
	flex-shrink: 0;
	opacity: 1;
	color: var(--accent);
	transform: none;
}
.contact-column .contact-link:hover svg {
	color: var(--accent-hover);
}
/* =========================================================
   LOCATION
========================================================= */
.footer-location {
	display: grid;
	grid-template-columns: auto minmax(0, 1fr) auto;
	align-items: center;
	gap: 1rem;
	padding: 1.3rem 0;
	color: var(--text-secondary);
	border-bottom: 1px solid var(--border);
	text-decoration: none;
	transition: color 0.2s ease;
}
.location-icon {
	display: grid;
	place-items: center;
	width: 32px;
	height: 32px;
	border: 1px solid var(--border);
	color: var(--accent);
	transition:
		border-color 0.2s ease,
		background 0.2s ease;
}
.location-content {
	display: flex;
	flex-direction: column;
	gap: 0.3rem;
}
.location-content span {
	color: var(--text-muted);
	font-size: 0.56rem;
	font-weight: 700;
	letter-spacing: 0.15em;
}
.location-content strong {
	color: var(--text-secondary);
	font-size: 0.76rem;
	font-weight: 500;
	line-height: 1.5;
}
.location-arrow {
	color: var(--accent);
	transition: transform 0.2s ease;
}
.footer-location:hover {
	color: var(--text);
}
.footer-location:hover .location-icon {
	border-color: var(--accent);
	background: var(--accent-soft);
}
.footer-location:hover .location-content strong {
	color: var(--text);
}
.footer-location:hover .location-arrow {
	transform: translate(3px, -3px);
}
/* =========================================================
   BOTTOM
========================================================= */
.footer-bottom {
	display: grid;
	grid-template-columns: 1fr auto 1fr;
	align-items: center;
	gap: 1rem;
	padding: 1.1rem 0;
	color: var(--text-muted);
	font-size: 0.6rem;
	letter-spacing: 0.05em;
}
.footer-location-code {
	justify-self: center;
}
.back-to-top {
	display: inline-flex;
	align-items: center;
	justify-content: flex-end;
	justify-self: end;
	gap: 0.6rem;
	padding: 0;
	border: 0;
	background: transparent;
	color: var(--text-secondary);
	cursor: pointer;
	font-family: inherit;
	font-size: 0.6rem;
	letter-spacing: 0.08em;
	transition: color 0.2s ease;
}
.back-to-top svg {
	color: var(--accent);
	transition: transform 0.2s ease;
}
.back-to-top:hover {
	color: var(--text);
}
.back-to-top:hover svg {
	transform: translateY(-3px);
}
/* =========================================================
   TABLET
========================================================= */
@media (max-width: 800px) {
	.footer-main {
		grid-template-columns: 1fr 1fr;
		gap: 2.5rem;
	}
	.contact-column {
		grid-column: 1 / -1;
	}
}
/* =========================================================
   MOBILE
========================================================= */
@media (max-width: 560px) {
	.footer-main {
		grid-template-columns: 1fr;
		gap: 0;
		padding: 2.5rem 0;
	}
	.footer-column {
		width: 100%;
		padding: 1.5rem 0;
		border-top: 1px solid var(--border);
	}
	.footer-column:first-child {
		padding-top: 0;
		border-top: 0;
	}
	.footer-column > a {
		max-width: 100%;
	}
	.contact-column {
		grid-column: auto;
	}
	.footer-location {
		grid-template-columns: auto minmax(0, 1fr);
	}
	.location-arrow {
		display: none;
	}
	.location-content strong {
		font-size: 0.7rem;
	}
	.footer-bottom {
		grid-template-columns: 1fr auto;
		gap: 0.75rem;
		padding: 1rem 0;
	}
	.footer-location-code {
		display: none;
	}
	.back-to-top {
		grid-column: 2;
		grid-row: 1;
	}
}
/* =========================================================
   SMALL MOBILE
========================================================= */
@media (max-width: 400px) {
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
