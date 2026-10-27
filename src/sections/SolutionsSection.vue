<script setup>
import SectionLabel from '@/components/SectionLabel.vue';
import SoftwarePlatforms from '@/components/SoftwarePlatforms.vue';
import { ArrowUpRight, Boxes, Calculator, PackageSearch, ShoppingBasket, UsersRound } from 'lucide-vue-next';
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
	<section id="solutions" class="solutions">
		<div class="solutions-container">
			<!-- INTRO -->
			<div class="solutions-intro">
				<div class="solutions-label">
					<SectionLabel number="02" title="Business Solutions" accent="blue" />
				</div>
				<div class="solutions-heading">
					<span class="heading-kicker">BUSINESS SYSTEMS</span>
					<h2>
						Technology
						<span>that works.</span>
					</h2>
					<p>The right business software should do more than store information. It should help your people work better, give you greater visibility and make everyday decisions easier.</p>
				</div>
			</div>
			<!-- SOLUTIONS -->
			<div class="solution-list">
				<article v-for="solution in solutions" :key="solution.number" class="solution-item">
					<div class="solution-number">
						{{ solution.number }}
					</div>
					<div class="solution-content">
						<div class="solution-main">
							<div>
								<span class="solution-category">
									{{ solution.shortName }}
								</span>
								<h3>
									{{ solution.name }}
								</h3>
							</div>
							<div class="solution-icon">
								<component :is="solution.icon" :size="21" :stroke-width="1.6" />
							</div>
						</div>
						<p>
							{{ solution.description }}
						</p>
					</div>
				</article>
			</div>
			<!-- SOFTWARE PLATFORMS -->
			<div class="platform-area">
				<SoftwarePlatforms />
			</div>
			<!-- CLOSING -->
			<div class="solutions-bottom">
				<div>
					<span>OUR APPROACH</span>
					<h3>
						Good software is not about having more tools.
						<span>It is about having the right ones.</span>
					</h3>
				</div>
				<ArrowUpRight class="bottom-arrow" :size="22" :stroke-width="1.5" />
			</div>
		</div>
	</section>
</template>
<style scoped>
/* ========================================
   SOLUTIONS
======================================== */
.solutions {
	background: var(--bg);
	color: var(--text);
	border-bottom: 1px solid var(--border);
}
.solutions-container {
	width: min(100%, var(--container));
	margin: 0 auto;
	padding: clamp(4rem, 6vw, 5.5rem) var(--page-padding);
}
/* ========================================
   INTRO
======================================== */
.solutions-intro {
	display: grid;
	grid-template-columns: 120px minmax(0, 1fr);
	gap: clamp(2rem, 4vw, 4rem);
	padding-bottom: 3.5rem;
	border-bottom: 1px solid var(--border);
}
.solutions-heading {
	max-width: 850px;
}
.heading-kicker {
	display: block;
	margin-bottom: 0.9rem;
	color: var(--accent);
	font-size: 0.62rem;
	font-weight: 650;
	letter-spacing: 0.14em;
}
.solutions-heading h2 {
	margin: 0;
	color: var(--text);
	font-size: clamp(2.8rem, 5vw, 5rem);
	font-weight: 650;
	line-height: 0.97;
	letter-spacing: -0.06em;
}
.solutions-heading h2 span {
	display: block;
	color: var(--accent);
}
.solutions-heading p {
	max-width: 650px;
	margin: 1.4rem 0 0;
	color: var(--text-secondary);
	font-size: clamp(0.95rem, 1.2vw, 1.05rem);
	line-height: 1.6;
}
/* ========================================
   SOLUTION LIST
======================================== */
.solution-list {
	border-top: 1px solid var(--border);
}
.solution-item {
	display: grid;
	grid-template-columns: 70px minmax(0, 1fr);
	border-bottom: 1px solid var(--border);
	transition: background 180ms ease;
}
.solution-item:hover {
	background: var(--accent-soft);
}
.solution-number {
	display: flex;
	align-items: flex-start;
	padding: 1.45rem 1rem;
	border-right: 1px solid var(--border);
	color: var(--text-muted);
	font-size: 0.62rem;
	font-weight: 650;
	letter-spacing: 0.08em;
}
.solution-content {
	padding: 1.45rem 1.5rem 1.55rem;
}
.solution-main {
	display: flex;
	align-items: flex-start;
	justify-content: space-between;
	gap: 2rem;
}
.solution-category {
	display: block;
	margin-bottom: 0.45rem;
	color: var(--accent);
	font-size: 0.57rem;
	font-weight: 650;
	letter-spacing: 0.14em;
}
.solution-main h3 {
	margin: 0;
	color: var(--text);
	font-size: clamp(1.35rem, 2vw, 2rem);
	font-weight: 600;
	line-height: 1.05;
	letter-spacing: -0.035em;
}
.solution-icon {
	flex-shrink: 0;
	display: grid;
	place-items: center;
	width: 40px;
	height: 40px;
	border: 1px solid var(--border);
	border-radius: var(--radius);
	background: var(--bg);
	color: var(--accent);
	transition:
		background 180ms ease,
		border-color 180ms ease,
		color 180ms ease;
}
.solution-item:hover .solution-icon {
	background: var(--accent);
	border-color: var(--accent);
	color: var(--text-inverse);
}
.solution-content > p {
	max-width: 650px;
	margin: 0.8rem 0 0;
	color: var(--text-secondary);
	font-size: 0.8rem;
	line-height: 1.55;
}
/* ========================================
   SOFTWARE PLATFORMS
======================================== */
.platform-area {
	margin-top: 4rem;
}
/* ========================================
   CLOSING
======================================== */
.solutions-bottom {
	display: flex;
	align-items: flex-end;
	justify-content: space-between;
	gap: 2rem;
	margin-top: 3.5rem;
	padding-top: 2rem;
	border-top: 1px solid var(--border);
}
.solutions-bottom > div {
	max-width: 700px;
}
.solutions-bottom > div > span {
	display: block;
	margin-bottom: 0.7rem;
	color: var(--text-muted);
	font-size: 0.6rem;
	font-weight: 650;
	letter-spacing: 0.12em;
}
.solutions-bottom h3 {
	margin: 0;
	color: var(--text);
	font-size: clamp(1.4rem, 2.3vw, 2.2rem);
	font-weight: 600;
	line-height: 1.08;
	letter-spacing: -0.04em;
}
.solutions-bottom h3 span {
	display: block;
	color: var(--text-secondary);
}
.bottom-arrow {
	flex-shrink: 0;
	color: var(--accent);
}
/* ========================================
   TABLET
======================================== */
@media (max-width: 900px) {
	.solutions-intro {
		grid-template-columns: 100px minmax(0, 1fr);
	}
	.solution-content {
		padding-right: 1.25rem;
		padding-left: 1.25rem;
	}
}
/* ========================================
   MOBILE
======================================== */
@media (max-width: 650px) {
	.solutions-container {
		padding-top: 3.5rem;
		padding-bottom: 3.5rem;
	}
	.solutions-intro {
		display: block;
		padding-bottom: 2.5rem;
	}
	.solutions-label {
		margin-bottom: 1.5rem;
	}
	.solutions-heading h2 {
		font-size: clamp(2.7rem, 12vw, 4rem);
		line-height: 0.97;
	}
	.solutions-heading p {
		margin-top: 1.2rem;
		font-size: 0.9rem;
		line-height: 1.6;
	}
	.solution-item {
		grid-template-columns: 45px minmax(0, 1fr);
	}
	.solution-number {
		padding: 1.35rem 0.7rem;
	}
	.solution-content {
		padding: 1.35rem 0.9rem 1.45rem;
	}
	.solution-main {
		gap: 1rem;
	}
	.solution-category {
		margin-bottom: 0.4rem;
	}
	.solution-main h3 {
		font-size: 1.3rem;
		line-height: 1.08;
	}
	.solution-icon {
		width: 36px;
		height: 36px;
	}
	.solution-content > p {
		margin-top: 0.75rem;
		font-size: 0.78rem;
		line-height: 1.55;
	}
	.platform-area {
		margin-top: 3rem;
	}
	.solutions-bottom {
		align-items: flex-start;
		margin-top: 2.75rem;
		padding-top: 1.75rem;
	}
	.solutions-bottom h3 {
		font-size: 1.45rem;
	}
	.bottom-arrow {
		margin-top: 0.1rem;
	}
}
</style>
