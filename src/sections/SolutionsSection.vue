<script setup>
import SectionLabel from '@/components/SectionLabel.vue';
import SoftwarePlatforms from '@/components/SoftwarePlatforms.vue';
import { Boxes, Calculator, PackageSearch, ShoppingBasket, UsersRound } from 'lucide-vue-next';
const solutions = [
	{
		number: '01',
		name: 'Accounting Software',
		shortName: 'ACCOUNTING',
		icon: Calculator,
		description: 'Manage finances, transactions and essential accounting processes with software built for clearer day-to-day business operations.',
	},
	{
		number: '02',
		name: 'Enterprise Resource Planning',
		shortName: 'ERP',
		icon: Boxes,
		description: 'Connect key areas of your organisation through integrated ERP systems that bring business processes together.',
	},
	{
		number: '03',
		name: 'Inventory Software',
		shortName: 'INVENTORY',
		icon: PackageSearch,
		description: 'Keep track of stock, movement and availability with inventory systems that give your business better visibility.',
	},
	{
		number: '04',
		name: 'Supermarket Software',
		shortName: 'RETAIL',
		icon: ShoppingBasket,
		description: 'Streamline retail and point-of-sale operations with practical software for supermarkets and growing retail businesses.',
	},
	{
		number: '05',
		name: 'HR Software',
		shortName: 'HUMAN RESOURCES',
		icon: UsersRound,
		description: 'Organise employee information and HR processes with digital tools that make people management easier.',
	},
];
</script>
<template>
	<section id="solutions" class="solutions site-section">
		<div class="section-inner">
			<!-- =================================================
			     SECTION INTRO
			================================================== -->
			<div class="solutions-header">
				<div class="solutions-label">
					<SectionLabel number="02" title="Business Solutions" accent="blue" />
					<span class="label-meta"> SOFTWARE / OPERATIONS / MANAGEMENT </span>
				</div>
				<div class="solutions-heading">
					<p class="heading-kicker">BUSINESS SYSTEMS</p>
					<h2>
						Technology
						<span>that works.</span>
					</h2>
					<p class="intro">The right business software should do more than store information. It should help your people work better, give you greater visibility and make everyday decisions easier.</p>
				</div>
			</div>
			<!-- =================================================
			     SOLUTION LIST
			================================================== -->
			<div class="solution-list">
				<article v-for="solution in solutions" :key="solution.number" class="solution-item">
					<div class="solution-number">
						{{ solution.number }}
					</div>
					<div class="solution-main">
						<div class="solution-title-row">
							<div class="solution-title">
								<span class="solution-category">
									{{ solution.shortName }}
								</span>
								<h3>
									{{ solution.name }}
								</h3>
							</div>
							<div class="solution-icon">
								<component :is="solution.icon" :size="25" :stroke-width="1.5" />
							</div>
						</div>
						<p class="solution-description">
							{{ solution.description }}
						</p>
					</div>
				</article>
			</div>
			<!-- =================================================
			     SOFTWARE PLATFORMS
			================================================== -->
			<div class="platform-area">
				<SoftwarePlatforms />
			</div>
		</div>
	</section>
</template>
<style scoped>
/* =========================================================
   SOLUTIONS
========================================================= */
.solutions {
	background: var(--bg);
	color: var(--text);
}
/* =========================================================
   HEADER
========================================================= */
.solutions-header {
	display: grid;
	grid-template-columns: 180px minmax(0, 1fr);
	gap: 3.5rem;
	padding: 5rem 0 4rem;
	border-bottom: 1px solid var(--border);
}
.solutions-label {
	display: flex;
	flex-direction: column;
	justify-content: space-between;
}
.label-meta {
	max-width: 130px;
	color: var(--text-muted);
	font-size: 0.58rem;
	font-weight: 650;
	line-height: 1.6;
	letter-spacing: 0.12em;
}
.solutions-heading {
	max-width: 850px;
}
.heading-kicker {
	margin: 0 0 1rem;
	color: var(--accent);
	font-size: 0.62rem;
	font-weight: 700;
	letter-spacing: 0.16em;
}
.solutions-heading h2 {
	margin: 0;
	font-size: clamp(3.2rem, 6vw, 6.2rem);
	font-weight: 600;
	line-height: 0.92;
	letter-spacing: -0.065em;
}
.solutions-heading h2 span {
	display: block;
	color: var(--accent);
}
.intro {
	max-width: 650px;
	margin: 2rem 0 0;
	color: var(--text-secondary);
	font-size: 0.95rem;
	line-height: 1.7;
}
/* =========================================================
   SOLUTION LIST
========================================================= */
.solution-list {
	border-top: 1px solid var(--border-strong);
}
.solution-item {
	display: grid;
	grid-template-columns: 70px minmax(0, 1fr);
	border-bottom: 1px solid var(--border);
	transition: background-color 0.25s ease;
}
.solution-item:hover {
	background: var(--accent-soft);
}
.solution-number {
	padding: 1.75rem 1rem;
	color: var(--text-muted);
	font-size: 0.65rem;
	font-weight: 700;
	letter-spacing: 0.1em;
	border-right: 1px solid var(--border);
}
.solution-main {
	padding: 1.75rem 2rem 2rem;
}
.solution-title-row {
	display: flex;
	align-items: flex-start;
	justify-content: space-between;
	gap: 2rem;
}
.solution-category {
	display: block;
	margin-bottom: 0.55rem;
	color: var(--accent);
	font-size: 0.56rem;
	font-weight: 700;
	letter-spacing: 0.16em;
}
.solution-title h3 {
	margin: 0;
	color: var(--text);
	font-size: clamp(1.45rem, 2.5vw, 2.35rem);
	font-weight: 450;
	line-height: 1.05;
	letter-spacing: -0.04em;
}
.solution-icon {
	flex-shrink: 0;
	display: grid;
	place-items: center;
	width: 42px;
	height: 42px;
	color: var(--accent);
	border: 1px solid var(--border);
	border-radius: 8px;
	background: var(--bg);
	transition:
		background-color 0.25s ease,
		color 0.25s ease;
}
.solution-item:hover .solution-icon {
	background: var(--accent);
	color: var(--text-inverse);
	border-color: var(--accent);
}
.solution-description {
	max-width: 650px;
	margin: 1rem 0 0;
	color: var(--text-secondary);
	font-size: 0.82rem;
	line-height: 1.7;
}
/* =========================================================
   PLATFORM AREA
========================================================= */
.platform-area {
	margin-top: 5rem;
}
/* =========================================================
   TABLET
========================================================= */
@media (max-width: 800px) {
	.solutions-header {
		grid-template-columns: 130px minmax(0, 1fr);
		gap: 2rem;
	}
	.solutions-heading h2 {
		font-size: clamp(3rem, 8vw, 5rem);
	}
	.solution-main {
		padding-right: 1.5rem;
		padding-left: 1.5rem;
	}
	.platform-area {
		margin-top: 4rem;
	}
}
/* =========================================================
   MOBILE
========================================================= */
@media (max-width: 600px) {
	.solutions-header {
		display: block;
		padding: 3.5rem 0 3rem;
	}
	.solutions-label {
		display: block;
	}
	.label-meta {
		display: block;
		margin-top: 1.25rem;
		max-width: none;
	}
	.solutions-heading {
		margin-top: 3rem;
	}
	.heading-kicker {
		margin-bottom: 0.9rem;
	}
	.solutions-heading h2 {
		font-size: clamp(2.8rem, 13vw, 4rem);
		line-height: 0.94;
	}
	.intro {
		margin-top: 1.5rem;
		font-size: 0.9rem;
	}
	.solution-item {
		grid-template-columns: 45px minmax(0, 1fr);
	}
	.solution-number {
		padding: 1.5rem 0.7rem;
	}
	.solution-main {
		padding: 1.5rem 1rem 1.7rem;
	}
	.solution-title-row {
		gap: 1rem;
	}
	.solution-title h3 {
		font-size: 1.45rem;
	}
	.solution-icon {
		width: 36px;
		height: 36px;
	}
	.solution-description {
		margin-top: 0.85rem;
		font-size: 0.78rem;
	}
	.platform-area {
		margin-top: 3.5rem;
	}
	.solutions-footer {
		margin-top: 3rem;
	}
}
</style>
