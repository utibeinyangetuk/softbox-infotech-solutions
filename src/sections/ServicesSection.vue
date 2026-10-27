<script setup>
import SectionLabel from '@/components/SectionLabel.vue';
import { ArrowRight, BriefcaseBusiness, GraduationCap, UserSearch, Wrench } from 'lucide-vue-next';
defineEmits(['go-to']);
const services = [
	{
		number: '01',
		title: 'Training & Mentorship',
		icon: GraduationCap,
		description: 'Practical training and mentorship that helps individuals and organisations confidently use business management software and get more value from their technology.',
	},
	{
		number: '02',
		title: 'Support & Maintenance',
		icon: Wrench,
		description: 'Dependable technical assistance and ongoing maintenance designed to keep your business software and technology solutions working effectively.',
	},
	{
		number: '03',
		title: 'Specialized Recruitment',
		icon: UserSearch,
		description: 'Specialized recruitment focused on identifying and connecting organisations with qualified professionals for finance and procurement roles.',
	},
	{
		number: '04',
		title: 'Personnel Outsourcing',
		icon: BriefcaseBusiness,
		description: 'Flexible outsourcing of skilled finance and procurement personnel to support operations, strengthen teams and meet changing workforce requirements.',
	},
];
</script>
<template>
	<section id="services" class="services-section">
		<div class="services-container">
			<!-- INTRO -->
			<div class="services-intro">
				<SectionLabel number="03" title="Services" accent="blue" />
				<div class="intro-content">
					<h2>
						Technology needs
						<span>the right people behind it.</span>
					</h2>
					<p>We stay involved beyond implementation. From training and technical support to specialist recruitment and personnel outsourcing, we help businesses build the knowledge, support and people they need to operate effectively.</p>
				</div>
			</div>
			<!-- SERVICES -->
			<div class="services-list">
				<article v-for="service in services" :key="service.number" class="service-row">
					<div class="service-number">
						{{ service.number }}
					</div>
					<div class="service-icon">
						<component :is="service.icon" :size="20" :stroke-width="1.6" />
					</div>
					<div class="service-content">
						<h3>{{ service.title }}</h3>
						<p>
							{{ service.description }}
						</p>
					</div>
					<button class="service-action" type="button" @click="$emit('go-to', 'contact')" :aria-label="`Enquire about ${service.title}`">
						<span>ENQUIRE</span>
						<ArrowRight :size="16" />
					</button>
				</article>
			</div>
			<!-- APPROACH -->
			<div class="services-approach">
				<div class="approach-label">
					<span>OUR APPROACH</span>
				</div>
				<div class="approach-content">
					<h3>
						Good technology works better
						<span>when people understand it.</span>
					</h3>
					<p>We combine technology, practical knowledge, ongoing support and specialist talent to help organisations work with greater confidence.</p>
				</div>
			</div>
			<!-- CTA -->
			<div class="services-cta">
				<div>
					<span>READY TO TALK?</span>
					<h3>
						Tell us what
						<span>your business needs.</span>
					</h3>
				</div>
				<button class="cta-button" type="button" @click="$emit('go-to', 'contact')">
					<span>Talk to Softbox</span>
					<ArrowRight :size="17" />
				</button>
			</div>
		</div>
	</section>
</template>
<style scoped>
.services-section {
	background: var(--bg);
	color: var(--text);
	border-top: 1px solid var(--border);
}
.services-container {
	width: min(100%, var(--container));
	margin: 0 auto;
	padding: 5rem var(--page-padding) 5.5rem;
}
/* =========================
   INTRO
========================= */
.services-intro {
	display: grid;
	grid-template-columns: 160px minmax(0, 1fr);
	gap: 2.5rem;
	padding-bottom: 4rem;
}
.intro-content {
	max-width: 850px;
}
.intro-content h2 {
	max-width: 820px;
	margin: 0;
	font-size: clamp(2.8rem, 5vw, 5rem);
	line-height: 0.98;
	font-weight: 650;
	letter-spacing: -0.055em;
}
.intro-content h2 span {
	display: block;
	color: var(--accent);
}
.intro-content p {
	max-width: 680px;
	margin: 1.6rem 0 0;
	color: var(--text-secondary);
	font-size: 1.02rem;
	line-height: 1.75;
}
/* =========================
   SERVICE LIST
========================= */
.services-list {
	border-top: 1px solid var(--border);
}
.service-row {
	display: grid;
	grid-template-columns: 60px 48px minmax(0, 1fr) 110px;
	align-items: center;
	gap: 1.5rem;
	min-height: 165px;
	padding: 2rem 0;
	border-bottom: 1px solid var(--border);
}
.service-number {
	align-self: start;
	padding-top: 0.25rem;
	color: var(--text-muted);
	font-size: 0.72rem;
	font-weight: 650;
	letter-spacing: 0.08em;
}
.service-icon {
	width: 44px;
	height: 44px;
	display: grid;
	place-items: center;
	border: 1px solid var(--border);
	color: var(--accent);
	border-radius: 50%;
}
.service-content {
	max-width: 760px;
}
.service-content h3 {
	margin: 0 0 0.65rem;
	font-size: clamp(1.4rem, 2.2vw, 2rem);
	line-height: 1.1;
	font-weight: 600;
	letter-spacing: -0.035em;
}
.service-content p {
	max-width: 650px;
	margin: 0;
	color: var(--text-secondary);
	font-size: 0.95rem;
	line-height: 1.65;
}
.service-action {
	display: inline-flex;
	align-items: center;
	justify-content: flex-end;
	gap: 0.55rem;
	padding: 0;
	border: 0;
	background: transparent;
	color: var(--text-muted);
	cursor: pointer;
	font-family: inherit;
	font-size: 0.64rem;
	font-weight: 700;
	letter-spacing: 0.1em;
	transition:
		color 0.2s ease,
		gap 0.2s ease;
}
.service-action svg {
	color: var(--accent);
}
.service-action:hover {
	gap: 0.8rem;
	color: var(--text);
}
/* =========================
   APPROACH
========================= */
.services-approach {
	display: grid;
	grid-template-columns: 160px minmax(0, 1fr);
	gap: 2.5rem;
	padding: 4.5rem 0;
	border-bottom: 1px solid var(--border);
}
.approach-label span {
	color: var(--text-muted);
	font-size: 0.65rem;
	font-weight: 650;
	letter-spacing: 0.12em;
}
.approach-content {
	max-width: 850px;
}
.approach-content h3 {
	max-width: 780px;
	margin: 0;
	font-size: clamp(2rem, 3.6vw, 3.6rem);
	line-height: 1;
	font-weight: 600;
	letter-spacing: -0.05em;
}
.approach-content h3 span {
	display: block;
	color: var(--accent);
}
.approach-content p {
	max-width: 600px;
	margin: 1.3rem 0 0;
	color: var(--text-secondary);
	font-size: 0.95rem;
	line-height: 1.7;
}
/* =========================
   CTA
========================= */
.services-cta {
	display: flex;
	align-items: flex-end;
	justify-content: space-between;
	gap: 2rem;
	padding-top: 4rem;
}
.services-cta > div > span {
	display: block;
	margin-bottom: 0.9rem;
	color: var(--text-muted);
	font-size: 0.65rem;
	font-weight: 650;
	letter-spacing: 0.12em;
}
.services-cta h3 {
	max-width: 650px;
	margin: 0;
	font-size: clamp(2rem, 4vw, 4rem);
	line-height: 0.98;
	font-weight: 600;
	letter-spacing: -0.05em;
}
.services-cta h3 span {
	display: block;
	color: var(--accent);
}
.cta-button {
	display: inline-flex;
	align-items: center;
	justify-content: space-between;
	gap: 2rem;
	min-width: 190px;
	padding: 0.95rem 1rem;
	border: 1px solid var(--text);
	background: var(--text);
	color: var(--text-inverse);
	cursor: pointer;
	font-family: inherit;
	font-size: 0.68rem;
	font-weight: 700;
	letter-spacing: 0.08em;
	transition:
		background 0.2s ease,
		border-color 0.2s ease;
}
.cta-button svg {
	color: var(--accent);
}
.cta-button:hover {
	background: var(--accent);
	border-color: var(--accent);
}
.cta-button:hover svg {
	color: var(--text-inverse);
}
/* =========================
   TABLET
========================= */
@media (max-width: 800px) {
	.services-container {
		padding-top: 4rem;
		padding-bottom: 4rem;
	}
	.services-intro,
	.services-approach {
		grid-template-columns: 1fr;
		gap: 1.5rem;
	}
	.services-intro {
		padding-bottom: 3rem;
	}
	.service-row {
		grid-template-columns: 50px 44px minmax(0, 1fr);
		gap: 1rem;
		padding: 1.75rem 0;
	}
	.service-action {
		grid-column: 3;
		justify-content: flex-start;
		margin-top: 0.25rem;
	}
	.services-approach {
		padding: 3.5rem 0;
	}
	.services-cta {
		align-items: flex-start;
		flex-direction: column;
		padding-top: 3.5rem;
	}
	.cta-button {
		width: 100%;
	}
}
/* =========================
   MOBILE
========================= */
@media (max-width: 520px) {
	.services-container {
		padding: 3.25rem var(--page-padding) 3.5rem;
	}
	.services-intro {
		gap: 1.5rem;
		padding-bottom: 2.5rem;
	}
	.intro-content h2 {
		font-size: clamp(2.45rem, 11vw, 3.4rem);
	}
	.intro-content p {
		margin-top: 1.2rem;
		font-size: 0.94rem;
		line-height: 1.65;
	}
	.service-row {
		grid-template-columns: 36px 40px minmax(0, 1fr);
		gap: 0.8rem;
		padding: 1.6rem 0;
	}
	.service-number {
		font-size: 0.68rem;
	}
	.service-icon {
		width: 38px;
		height: 38px;
	}
	.service-content {
		grid-column: 1 / -1;
		padding-top: 0.35rem;
	}
	.service-content h3 {
		font-size: 1.45rem;
	}
	.service-content p {
		font-size: 0.9rem;
		line-height: 1.6;
	}
	.service-action {
		grid-column: 1 / -1;
		margin-top: 0.3rem;
	}
	.services-approach {
		padding: 3rem 0;
	}
	.approach-content h3 {
		font-size: 2.15rem;
	}
	.approach-content p {
		font-size: 0.9rem;
	}
	.services-cta {
		padding-top: 3rem;
	}
	.services-cta h3 {
		font-size: 2.2rem;
	}
}
</style>
