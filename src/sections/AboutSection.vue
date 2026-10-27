<script setup>
import SectionLabel from '@/components/SectionLabel.vue';
import { Check, Cpu, UsersRound, Zap } from 'lucide-vue-next';

defineEmits(['go-to']);
</script>

<template>
	<section id="about" class="about-section">
		<div class="about-container">
			<!-- INTRO -->
			<div class="about-intro">
				<div class="about-label">
					<SectionLabel number="01" title="About Softbox" accent="blue" />
				</div>

				<div class="about-heading">
					<h2>
						Technology should
						<span>work for your business.</span>
					</h2>

					<p>Softbox Infotech Solutions helps businesses use technology with greater clarity, efficiency and confidence. We combine the right software, practical implementation and ongoing support to help businesses operate better.</p>
				</div>
			</div>

			<!-- STATEMENT -->
			<div class="about-statement">
				<div class="statement-marker">
					<Cpu :size="18" />
					<span>OUR APPROACH</span>
				</div>

				<div class="statement-content">
					<h3>
						We don't just provide software.
						<span>We help you make it work.</span>
					</h3>

					<p>From selecting the right business system to implementation, training and ongoing support, we stay focused on how the technology actually fits into your day-to-day operations.</p>
				</div>
			</div>

			<!-- BENEFITS -->
			<div class="about-benefits">
				<div class="benefit">
					<div class="benefit-number">01</div>

					<div class="benefit-icon">
						<Zap :size="18" />
					</div>

					<div class="benefit-content">
						<h3>Work smarter</h3>
						<p>Reduce unnecessary manual work with systems designed around the way your business operates.</p>
					</div>
				</div>

				<div class="benefit">
					<div class="benefit-number">02</div>

					<div class="benefit-icon">
						<Cpu :size="18" />
					</div>

					<div class="benefit-content">
						<h3>Choose with confidence</h3>
						<p>Get practical guidance on the software and systems that make sense for your business.</p>
					</div>
				</div>

				<div class="benefit">
					<div class="benefit-number">03</div>

					<div class="benefit-icon">
						<UsersRound :size="18" />
					</div>

					<div class="benefit-content">
						<h3>Keep your team ready</h3>
						<p>Equip your people with the training, mentorship and support they need to use technology effectively.</p>
					</div>
				</div>
			</div>

			<!-- CAPABILITIES -->
			<div class="capabilities">
				<div class="capabilities-intro">
					<span>WHAT WE BRING</span>
					<p>Technology, people and support working together.</p>
				</div>

				<div class="capabilities-list">
					<div class="capability">
						<Check :size="15" />
						<span>Business management software</span>
					</div>

					<div class="capability">
						<Check :size="15" />
						<span>Accounting &amp; financial systems</span>
					</div>

					<div class="capability">
						<Check :size="15" />
						<span>ERP &amp; inventory solutions</span>
					</div>

					<div class="capability">
						<Check :size="15" />
						<span>Retail &amp; supermarket systems</span>
					</div>

					<div class="capability">
						<Check :size="15" />
						<span>HR management software</span>
					</div>

					<div class="capability">
						<Check :size="15" />
						<span>Training &amp; ongoing support</span>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<style scoped>
/* ========================================
   ABOUT
======================================== */

.about-section {
	background: var(--bg);
	color: var(--text);
	border-bottom: 1px solid var(--border);
}

.about-container {
	width: min(100%, var(--container));
	margin: 0 auto;
	padding: clamp(4rem, 6vw, 5.5rem) var(--page-padding);
}

/* ========================================
   INTRO
======================================== */

.about-intro {
	display: grid;
	grid-template-columns: 120px minmax(0, 1fr);

	gap: clamp(2rem, 4vw, 4rem);

	padding-bottom: 3.5rem;

	border-bottom: 1px solid var(--border);
}

.about-heading {
	max-width: 900px;
}

.about-heading h2 {
	margin: 0;

	color: var(--text);

	font-size: clamp(2.8rem, 5vw, 5rem);
	font-weight: 650;

	line-height: 0.97;
	letter-spacing: -0.06em;
}

.about-heading h2 span {
	display: block;
	color: var(--accent);
}

.about-heading p {
	max-width: 680px;

	margin: 1.5rem 0 0;

	color: var(--text-secondary);

	font-size: clamp(0.95rem, 1.2vw, 1.08rem);
	line-height: 1.65;
}

/* ========================================
   STATEMENT
======================================== */

.about-statement {
	display: grid;
	grid-template-columns: 1fr 1.7fr;

	gap: 2rem;

	padding: 3rem 0;

	border-bottom: 1px solid var(--border);
}

.statement-marker {
	display: flex;
	align-items: flex-start;

	gap: 0.65rem;

	color: var(--accent);

	font-size: 0.62rem;
	font-weight: 650;

	letter-spacing: 0.12em;
}

.statement-marker svg {
	flex-shrink: 0;
}

.statement-content {
	max-width: 760px;
}

.statement-content h3 {
	margin: 0;

	color: var(--text);

	font-size: clamp(1.8rem, 3vw, 3rem);
	font-weight: 600;

	line-height: 1.05;
	letter-spacing: -0.045em;
}

.statement-content h3 span {
	display: block;
	color: var(--text-secondary);
}

.statement-content p {
	max-width: 620px;

	margin: 1rem 0 0;

	color: var(--text-secondary);

	font-size: 0.9rem;
	line-height: 1.6;
}

/* ========================================
   BENEFITS
======================================== */

.about-benefits {
	display: grid;
	grid-template-columns: repeat(3, 1fr);

	border-bottom: 1px solid var(--border);
}

.benefit {
	position: relative;

	min-height: 185px;

	padding: 1.3rem 1.35rem 1.5rem;

	border-left: 1px solid var(--border);
}

.benefit:first-child {
	border-left: 0;
}

.benefit-number {
	color: var(--accent);

	font-size: 0.62rem;
	font-weight: 650;

	letter-spacing: 0.08em;
}

.benefit-icon {
	display: flex;
	align-items: center;
	justify-content: center;

	width: 36px;
	height: 36px;

	margin-top: 1.5rem;

	border: 1px solid var(--border);

	background: var(--bg-secondary);
	color: var(--accent);
}

.benefit-content {
	margin-top: 1rem;
}

.benefit-content h3 {
	margin: 0 0 0.45rem;

	color: var(--text);

	font-size: 0.98rem;
	font-weight: 650;
}

.benefit-content p {
	max-width: 260px;

	margin: 0;

	color: var(--text-secondary);

	font-size: 0.77rem;
	line-height: 1.5;
}

/* ========================================
   CAPABILITIES
======================================== */

.capabilities {
	display: grid;
	grid-template-columns: 1fr 2fr;

	gap: 2rem;

	padding: 3rem 0;
}

.capabilities-intro > span {
	display: block;

	color: var(--accent);

	font-size: 0.62rem;
	font-weight: 650;

	letter-spacing: 0.12em;
}

.capabilities-intro p {
	max-width: 220px;

	margin: 0.65rem 0 0;

	color: var(--text-secondary);

	font-size: 0.82rem;
	line-height: 1.5;
}

.capabilities-list {
	display: grid;
	grid-template-columns: 1fr 1fr;

	border-top: 1px solid var(--border);
	border-left: 1px solid var(--border);
}

.capability {
	display: flex;
	align-items: center;

	gap: 0.65rem;

	min-height: 52px;

	padding: 0 0.9rem;

	border-right: 1px solid var(--border);
	border-bottom: 1px solid var(--border);

	color: var(--text-secondary);

	font-size: 0.78rem;
	line-height: 1.4;
}

.capability svg {
	flex-shrink: 0;
	color: var(--accent);
}

/* ========================================
   TABLET
======================================== */

@media (max-width: 900px) {
	.about-intro {
		grid-template-columns: 100px minmax(0, 1fr);
	}

	.about-statement {
		grid-template-columns: 100px minmax(0, 1fr);
	}

	.capabilities {
		grid-template-columns: 1fr;
	}

	.capabilities-intro p {
		max-width: 320px;
	}
}

/* ========================================
   MOBILE
======================================== */

@media (max-width: 650px) {
	.about-container {
		padding-top: 3.5rem;
		padding-bottom: 3.5rem;
	}

	.about-intro {
		display: block;
		padding-bottom: 2.5rem;
	}

	.about-label {
		margin-bottom: 1.5rem;
	}

	.about-heading h2 {
		font-size: clamp(2.7rem, 12vw, 4rem);
		line-height: 0.97;
	}

	.about-heading p {
		margin-top: 1.25rem;
		font-size: 0.94rem;
		line-height: 1.6;
	}

	.about-statement {
		display: block;
		padding: 2.25rem 0;
	}

	.statement-marker {
		margin-bottom: 1.25rem;
	}

	.statement-content h3 {
		font-size: 1.75rem;
	}

	.statement-content p {
		margin-top: 0.8rem;
		font-size: 0.84rem;
	}

	.about-benefits {
		display: block;
	}

	.benefit,
	.benefit:first-child {
		min-height: auto;

		padding: 1.2rem 0 1.3rem;

		border-left: 0;
		border-bottom: 1px solid var(--border);
	}

	.benefit-icon {
		margin-top: 1.1rem;
	}

	.benefit-content {
		margin-top: 0.8rem;
	}

	.benefit-content p {
		max-width: none;
	}

	.capabilities {
		display: block;
		padding: 2.25rem 0 0;
	}

	.capabilities-intro {
		margin-bottom: 1.25rem;
	}

	.capabilities-list {
		grid-template-columns: 1fr;
	}

	.capability {
		min-height: 48px;
	}
}
</style>
