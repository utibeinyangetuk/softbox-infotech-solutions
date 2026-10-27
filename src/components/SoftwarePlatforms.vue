<script setup>
import SectionLabel from '@/components/SectionLabel.vue';
import { ArrowUpRight } from 'lucide-vue-next';

import erpnextLogo from '@/assets/logos/erpnext.svg';
import quickbooksLogo from '@/assets/logos/quickbooks.svg';
import sageLogo from '@/assets/logos/sage.svg';
import zohoLogo from '@/assets/logos/zoho-books.svg';

const platforms = [
	{
		number: '01',
		name: 'Zoho Books',
		type: 'Accounting & Finance',
		logo: zohoLogo,
		url: 'https://www.zoho.com/books/',
	},
	{
		number: '02',
		name: 'QuickBooks Online',
		type: 'Accounting & Finance',
		logo: quickbooksLogo,
		url: 'https://quickbooks.intuit.com/',
	},
	{
		number: '03',
		name: 'Sage',
		type: 'Business Management',
		logo: sageLogo,
		url: 'https://www.sage.com/',
	},
	{
		number: '04',
		name: 'ERPNext',
		type: 'ERP & Business Management',
		logo: erpnextLogo,
		url: 'https://erpnext.com/',
	},
];
</script>

<template>
	<section class="platforms-section">
		<div class="platforms-container">
			<!-- INTRO -->
			<div class="platforms-intro">
				<SectionLabel number="02.1" title="Software Platforms" accent="blue" />

				<div class="platforms-heading">
					<h2>
						Software we
						<span>work with.</span>
					</h2>

					<p>We work with established business software platforms and help organisations choose, implement and use the right system for their needs.</p>
				</div>
			</div>

			<!-- PLATFORM LIST -->
			<div class="platform-list">
				<a v-for="platform in platforms" :key="platform.number" :href="platform.url" target="_blank" rel="noopener noreferrer" class="platform-row">
					<span class="platform-number">
						{{ platform.number }}
					</span>

					<div class="platform-logo">
						<img :src="platform.logo" :alt="`${platform.name} logo`" />
					</div>

					<div class="platform-info">
						<h3>{{ platform.name }}</h3>
						<span>{{ platform.type }}</span>
					</div>

					<ArrowUpRight class="platform-arrow" :size="19" :stroke-width="1.7" />
				</a>
			</div>

			<!-- FOOTNOTE -->
			<div class="platform-note">
				<span>MORE THAN SOFTWARE</span>

				<p>Our role is not simply to provide software. We help businesses select the right system, configure it around their operations, train their teams and provide ongoing support.</p>
			</div>
		</div>
	</section>
</template>

<style scoped>
.platforms-section {
	background: var(--bg-secondary);
	border-top: 1px solid var(--border);
}

.platforms-container {
	max-width: var(--container);
	margin: 0 auto;
	padding: 4.5rem var(--page-padding);
}

/* INTRO */

.platforms-intro {
	display: grid;
	grid-template-columns: 180px 1fr;
	gap: 3rem;

	padding-bottom: 3rem;
}

.platforms-heading {
	max-width: 850px;
}

.platforms-heading h2 {
	margin: 0;

	font-size: clamp(2.5rem, 4.8vw, 4.8rem);
	line-height: 0.98;
	letter-spacing: -0.055em;
	font-weight: 650;
}

.platforms-heading h2 span {
	display: block;
	color: var(--accent);
}

.platforms-heading p {
	max-width: 650px;
	margin: 1.4rem 0 0;

	color: var(--text-secondary);
	font-size: 1rem;
	line-height: 1.7;
}

/* PLATFORM LIST */

.platform-list {
	border-top: 1px solid var(--border-strong);
}

.platform-row {
	display: grid;
	grid-template-columns: 60px 150px minmax(0, 1fr) 30px;
	align-items: center;
	gap: 1.5rem;

	min-height: 110px;
	padding: 1.25rem 0;

	color: var(--text);
	text-decoration: none;

	border-bottom: 1px solid var(--border);

	transition:
		background-color 0.2s ease,
		padding-left 0.2s ease;
}

.platform-row:hover {
	padding-left: 0.75rem;
	background: var(--bg);
}

/* NUMBER */

.platform-number {
	color: var(--text-muted);

	font-size: 0.72rem;
	font-weight: 650;
	letter-spacing: 0.08em;
}

/* LOGO */

.platform-logo {
	width: 135px;
	height: 58px;

	display: flex;
	align-items: center;
	justify-content: flex-start;
}

.platform-logo img {
	display: block;

	max-width: 125px;
	max-height: 48px;

	width: auto;
	height: auto;

	object-fit: contain;
}

/* INFO */

.platform-info h3 {
	margin: 0;

	font-size: 1.35rem;
	line-height: 1.15;
	font-weight: 600;
	letter-spacing: -0.025em;
}

.platform-info span {
	display: block;

	margin-top: 0.35rem;

	color: var(--text-secondary);

	font-size: 0.72rem;
	font-weight: 600;
	letter-spacing: 0.08em;
	text-transform: uppercase;
}

/* ARROW */

.platform-arrow {
	color: var(--accent);

	transition:
		transform 0.2s ease,
		color 0.2s ease;
}

.platform-row:hover .platform-arrow {
	transform: translate(2px, -2px);
}

/* NOTE */

.platform-note {
	display: grid;
	grid-template-columns: 180px 1fr;
	gap: 3rem;

	margin-top: 3rem;
	padding-top: 2rem;

	border-top: 1px solid var(--border);
}

.platform-note > span {
	color: var(--accent);

	font-size: 0.68rem;
	font-weight: 650;
	letter-spacing: 0.12em;
}

.platform-note p {
	max-width: 680px;
	margin: 0;

	color: var(--text-secondary);

	font-size: 0.95rem;
	line-height: 1.7;
}

/* TABLET */

@media (max-width: 800px) {
	.platforms-container {
		padding-top: 4rem;
		padding-bottom: 4rem;
	}

	.platforms-intro,
	.platform-note {
		grid-template-columns: 1fr;
		gap: 1.5rem;
	}

	.platform-row {
		grid-template-columns: 45px 120px minmax(0, 1fr) 25px;
		gap: 1rem;
	}
}

/* MOBILE */

@media (max-width: 560px) {
	.platforms-container {
		padding: 3.5rem var(--page-padding);
	}

	.platforms-heading h2 {
		font-size: clamp(2.4rem, 10vw, 3.5rem);
	}

	.platforms-heading p {
		font-size: 0.94rem;
	}

	.platform-row {
		grid-template-columns: 34px 1fr 22px;
		gap: 0.8rem;

		min-height: 92px;
	}

	.platform-logo {
		width: 100%;
		height: 42px;
	}

	.platform-logo img {
		max-width: 110px;
		max-height: 38px;
	}

	.platform-info {
		grid-column: 2;
	}

	.platform-info h3 {
		font-size: 1.05rem;
	}

	.platform-info span {
		font-size: 0.62rem;
	}

	.platform-arrow {
		grid-column: 3;
		grid-row: 1 / span 2;
	}

	.platform-note p {
		font-size: 0.9rem;
	}
}
</style>
