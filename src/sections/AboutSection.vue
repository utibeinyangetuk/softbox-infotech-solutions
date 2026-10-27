<script setup>
import SectionLabel from '@/components/SectionLabel.vue';
import { ArrowRight, Check } from 'lucide-vue-next';
defineEmits(['go-to']);
</script>
<template>
	<section id="home" class="home-section">
		<div class="home-container">
			<!-- Hero -->
			<div class="hero">
				<div class="hero-main">
					<SectionLabel number="00" title="Introduction" accent="blue" />
					<div class="hero-copy">
						<h1>
							Technology that
							<span>moves business forward.</span>
						</h1>
						<p class="hero-lead">Softbox helps businesses make better use of technology. We provide practical business software solutions, implementation, training and ongoing support — alongside the people and expertise needed to operate effectively.</p>
						<button type="button" class="primary-button" @click="$emit('go-to', 'solutions')">
							Explore our solutions
							<ArrowRight :size="17" />
						</button>
					</div>
				</div>
				<!-- Company statement -->
				<div class="hero-statement">
					<div class="statement-line"></div>
					<div class="statement-content">
						<span class="statement-label"> OUR APPROACH </span>
						<h2>
							The right technology
							<span>should make work easier.</span>
						</h2>
						<p>We help you choose the right system, put it to work, train your team and stay available when you need support.</p>
					</div>
				</div>
			</div>
			<!-- What we do -->
			<div class="home-services">
				<div class="services-intro">
					<span>WHAT WE DO</span>
					<p>Practical solutions built around the way your business works.</p>
				</div>
				<div class="service-item">
					<div class="service-top">
						<span>01</span>
					</div>
					<h3>Business Software</h3>
					<p>Accounting, ERP, inventory, retail and HR systems selected around your operational needs.</p>
				</div>
				<div class="service-item">
					<div class="service-top">
						<span>02</span>
					</div>
					<h3>Implementation &amp; Support</h3>
					<p>Setup, configuration, training, mentorship and dependable ongoing technical support.</p>
				</div>
				<div class="service-item">
					<div class="service-top">
						<span>03</span>
					</div>
					<h3>People &amp; Operations</h3>
					<p>Specialized finance and procurement recruitment and personnel outsourcing.</p>
				</div>
			</div>
			<!-- Bottom line -->
			<div class="home-bottom">
				<div class="bottom-points">
					<span>
						<Check :size="14" />
						Practical
					</span>
					<span>
						<Check :size="14" />
						Business-focused
					</span>
					<span>
						<Check :size="14" />
						Ongoing support
					</span>
				</div>
			</div>
		</div>
	</section>
</template>
<style scoped>
.home-section {
	background: var(--bg);
	border-bottom: 1px solid var(--border);
}
.home-container {
	width: min(100%, var(--container));
	min-height: calc(100svh - var(--header-height));
	margin: 0 auto;
	padding: 0 var(--page-padding);
	display: flex;
	flex-direction: column;
}
/* ----------------------------------
   HERO
---------------------------------- */
.hero {
	flex: 1;
	display: grid;
	grid-template-columns: minmax(0, 1.5fr) minmax(280px, 0.65fr);
	gap: clamp(3rem, 6vw, 7rem);
	padding: clamp(2.75rem, 4vw, 4rem) 0 3rem;
}
.hero-main {
	display: grid;
	grid-template-columns: 120px minmax(0, 1fr);
	gap: clamp(2rem, 4vw, 4rem);
}
.hero-copy {
	max-width: 820px;
}
.hero-copy h1 {
	margin: 0;
	color: var(--text);
	font-size: clamp(3rem, 5.5vw, 5.8rem);
	font-weight: 650;
	line-height: 0.99;
	letter-spacing: -0.06em;
}
.hero-copy h1 span {
	display: block;
	color: var(--accent);
}
.hero-lead {
	max-width: 680px;
	margin: 1.7rem 0 0;
	color: var(--text-secondary);
	font-size: clamp(1.05rem, 1.3vw, 1.18rem);
	line-height: 1.65;
}
/* ----------------------------------
   PRIMARY ACTION
---------------------------------- */
.primary-button {
	display: inline-flex;
	align-items: center;
	gap: 0.7rem;
	min-height: 46px;
	margin-top: 1.75rem;
	padding: 0 1.1rem;
	border: 1px solid var(--text);
	background: var(--text);
	color: var(--text-inverse);
	font-family: inherit;
	font-size: 0.84rem;
	font-weight: 650;
	cursor: pointer;
	transition:
		background 180ms ease,
		border-color 180ms ease,
		transform 180ms ease;
}
.primary-button:hover {
	background: var(--accent);
	border-color: var(--accent);
	transform: translateY(-1px);
}
/* ----------------------------------
   COMPANY STATEMENT
---------------------------------- */
.hero-statement {
	align-self: end;
	display: flex;
	gap: 1.5rem;
	margin-bottom: 0.5rem;
}
.statement-line {
	width: 2px;
	min-height: 150px;
	background: var(--accent);
	flex: 0 0 2px;
}
.statement-content {
	max-width: 340px;
}
.statement-label {
	display: block;
	margin-bottom: 1rem;
	color: var(--text-muted);
	font-size: 0.68rem;
	font-weight: 650;
	letter-spacing: 0.12em;
}
.statement-content h2 {
	margin: 0;
	color: var(--text);
	font-size: clamp(1.7rem, 2.5vw, 2.5rem);
	font-weight: 600;
	line-height: 1.06;
	letter-spacing: -0.04em;
}
.statement-content h2 span {
	display: block;
	color: var(--text-secondary);
}
.statement-content p {
	margin: 1rem 0 0;
	color: var(--text-secondary);
	font-size: 0.92rem;
	line-height: 1.6;
}
/* ----------------------------------
   WHAT WE DO
---------------------------------- */
.home-services {
	display: grid;
	grid-template-columns: 1.05fr repeat(3, 1fr);
	border-top: 1px solid var(--border);
}
.services-intro,
.service-item {
	min-height: 185px;
	padding: 1.3rem 1.35rem;
}
.services-intro {
	padding-left: 0;
	padding-right: 2rem;
}
.services-intro > span {
	display: block;
	color: var(--accent);
	font-size: 0.68rem;
	font-weight: 650;
	letter-spacing: 0.12em;
}
.services-intro p {
	max-width: 220px;
	margin: 0.75rem 0 0;
	color: var(--text-secondary);
	font-size: 0.9rem;
	line-height: 1.5;
}
.service-item {
	border-left: 1px solid var(--border);
}
.service-top {
	margin-bottom: 2.5rem;
}
.service-top span {
	color: var(--accent);
	font-size: 0.68rem;
	font-weight: 650;
}
.service-item h3 {
	margin: 0 0 0.55rem;
	color: var(--text);
	font-size: 1rem;
	font-weight: 650;
	line-height: 1.2;
}
.service-item p {
	max-width: 250px;
	margin: 0;
	color: var(--text-secondary);
	font-size: 0.8rem;
	line-height: 1.5;
}
/* ----------------------------------
   BOTTOM
---------------------------------- */
.home-bottom {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding: 1rem 0;
	border-top: 1px solid var(--border);
}
.bottom-points {
	display: flex;
	align-items: center;
	gap: 1.5rem;
}
.bottom-points span {
	display: inline-flex;
	align-items: center;
	gap: 0.35rem;
	color: var(--text-secondary);
	font-size: 0.72rem;
	font-weight: 550;
}
.bottom-points svg {
	color: var(--accent);
}
.contact-link {
	display: inline-flex;
	align-items: center;
	gap: 0.55rem;
	padding: 0;
	border: 0;
	background: transparent;
	color: var(--text);
	font-family: inherit;
	font-size: 0.78rem;
	font-weight: 650;
	cursor: pointer;
	transition: color 180ms ease;
}
.contact-link:hover {
	color: var(--accent);
}
/* ----------------------------------
   TABLET
---------------------------------- */
@media (max-width: 1000px) {
	.hero {
		grid-template-columns: 1fr;
		gap: 3rem;
	}
	.hero-statement {
		margin-left: 120px;
	}
	.home-services {
		grid-template-columns: 1fr 1fr;
	}
	.services-intro {
		border-bottom: 1px solid var(--border);
	}
	.service-item {
		border-bottom: 1px solid var(--border);
	}
	.service-item:nth-child(odd) {
		border-right: 1px solid var(--border);
	}
}
/* ----------------------------------
   MOBILE
---------------------------------- */
@media (max-width: 650px) {
	.home-container {
		min-height: auto;
	}
	.hero {
		display: block;
		padding: 2rem 0 2.25rem;
	}
	.hero-main {
		display: block;
	}
	.hero-main :deep(.section-label) {
		margin-bottom: 1.75rem;
	}
	.hero-copy h1 {
		font-size: clamp(2.8rem, 12vw, 4rem);
		line-height: 0.98;
	}
	.hero-lead {
		margin-top: 1.35rem;
		font-size: 1rem;
		line-height: 1.62;
	}
	.primary-button {
		margin-top: 1.5rem;
	}
	.hero-statement {
		margin: 2.75rem 0 0;
		gap: 1rem;
	}
	.statement-line {
		min-height: 115px;
	}
	.statement-content {
		max-width: none;
	}
	.statement-label {
		margin-bottom: 0.7rem;
	}
	.statement-content h2 {
		font-size: 1.65rem;
	}
	.statement-content p {
		margin-top: 0.8rem;
		font-size: 0.9rem;
	}
	.home-services {
		display: block;
	}
	.services-intro {
		min-height: auto;
		padding: 1.2rem 0 1rem;
	}
	.services-intro p {
		max-width: 300px;
	}
	.service-item {
		min-height: auto;
		padding: 1.15rem 0 1.25rem;
		border-left: 0;
		border-bottom: 1px solid var(--border);
	}
	.service-item:nth-child(odd) {
		border-right: 0;
	}
	.service-top {
		margin-bottom: 1.15rem;
	}
	.service-item h3 {
		font-size: 1rem;
	}
	.service-item p {
		max-width: 100%;
		font-size: 0.82rem;
	}
	.home-bottom {
		align-items: flex-start;
		flex-direction: column;
		gap: 1rem;
		padding: 1.15rem 0;
	}
	.bottom-points {
		flex-wrap: wrap;
		gap: 0.65rem 1rem;
	}
	.bottom-points span {
		font-size: 0.7rem;
	}
}
</style>
