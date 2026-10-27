<script setup>
import { ArrowDownRight, ArrowUpRight, Boxes, GraduationCap, Headphones } from 'lucide-vue-next';

defineEmits(['go-to']);
</script>

<template>
	<section id="home" class="home">
		<div class="home-container">
			<!-- Top identity -->
			<div class="topbar">
				<div class="brand-line">
					<span class="brand-mark"></span>
					<span>SOFTBOX INFOTECH SOLUTIONS LTD</span>
				</div>

				<span class="location">PORT HARCOURT · NIGERIA</span>
			</div>

			<!-- Main hero -->
			<div class="hero">
				<!-- Left -->
				<div class="hero-left">
					<span class="hero-number">01</span>

					<div class="hero-copy">
						<p class="eyebrow">BUSINESS TECHNOLOGY CONSULTANCY</p>

						<h1>
							Make your
							<span>business work</span>
							better.
						</h1>

						<p class="intro">The right software. The right systems. The right people to keep your business moving.</p>

						<div class="actions">
							<button type="button" class="primary-action" @click="$emit('go-to', 'solutions')">
								<span>Explore solutions</span>
								<ArrowUpRight :size="18" />
							</button>

							<button type="button" class="text-action" @click="$emit('go-to', 'about')">
								<span>About Softbox</span>
								<ArrowDownRight :size="17" />
							</button>
						</div>
					</div>
				</div>

				<!-- Right -->
				<div class="hero-right">
					<div class="system-panel">
						<div class="panel-top">
							<span>SOFTBOX / 01</span>
							<span>BUSINESS SYSTEMS</span>
						</div>

						<div class="panel-main">
							<div class="panel-icon">
								<Boxes :size="42" :stroke-width="1.1" />
							</div>

							<div>
								<span class="panel-label">WHAT WE DO</span>

								<h2>
									Technology
									<br />
									that fits
									<strong>your business.</strong>
								</h2>
							</div>
						</div>

						<div class="panel-list">
							<div>
								<span>01</span>
								<p>Business software</p>
							</div>

							<div>
								<span>02</span>
								<p>Implementation & training</p>
							</div>

							<div>
								<span>03</span>
								<p>Ongoing support</p>
							</div>

							<div>
								<span>04</span>
								<p>Finance & procurement talent</p>
							</div>
						</div>

						<div class="panel-bottom">
							<span>SOFTWARE</span>
							<span>PEOPLE</span>
							<span>SUPPORT</span>
						</div>
					</div>
				</div>
			</div>

			<!-- Services -->
			<div class="services">
				<button type="button" @click="$emit('go-to', 'solutions')">
					<div class="service-icon">
						<Boxes :size="19" :stroke-width="1.4" />
					</div>

					<div class="service-content">
						<small>01</small>
						<span>Business Solutions</span>
					</div>

					<ArrowUpRight :size="16" />
				</button>

				<button type="button" @click="$emit('go-to', 'services')">
					<div class="service-icon">
						<GraduationCap :size="19" :stroke-width="1.4" />
					</div>

					<div class="service-content">
						<small>02</small>
						<span>Training & Mentorship</span>
					</div>

					<ArrowUpRight :size="16" />
				</button>

				<button type="button" @click="$emit('go-to', 'services')">
					<div class="service-icon">
						<Headphones :size="19" :stroke-width="1.4" />
					</div>

					<div class="service-content">
						<small>03</small>
						<span>Support & Maintenance</span>
					</div>

					<ArrowUpRight :size="16" />
				</button>
			</div>

			<!-- Bottom -->
			<div class="bottom-line">
				<button type="button" @click="$emit('go-to', 'about')">
					<span>SCROLL TO DISCOVER</span>
					<ArrowDownRight :size="15" />
				</button>

				<span>EST. / BUSINESS SYSTEMS</span>

				<span>© SOFTBOX</span>
			</div>
		</div>
	</section>
</template>

<style scoped>
.home {
	min-height: 100svh;
	background: var(--bg);
	color: var(--text);
	border-bottom: 1px solid var(--border);
}

.home-container {
	width: min(calc(100% - (var(--page-padding) * 2)), var(--container));

	min-height: 100svh;
	margin: 0 auto;

	display: flex;
	flex-direction: column;
}

/* ================================
   TOP BAR
================================ */

.topbar {
	height: calc(var(--header-height) + 2rem);

	display: flex;
	align-items: flex-end;
	justify-content: space-between;

	padding-bottom: 1rem;

	border-bottom: 1px solid var(--border);

	font-size: 0.65rem;
	font-weight: 650;
	letter-spacing: 0.12em;
}

.brand-line {
	display: flex;
	align-items: center;
	gap: 0.6rem;

	color: var(--accent);
}

.brand-mark {
	width: 7px;
	height: 7px;

	display: block;

	background: var(--accent);
}

.location {
	color: var(--text-muted);
}

/* ================================
   HERO
================================ */

.hero {
	flex: 1;

	display: grid;
	grid-template-columns: 1.15fr 0.85fr;

	min-height: 0;
}

/* ================================
   LEFT
================================ */

.hero-left {
	position: relative;

	display: flex;
	align-items: center;

	padding: 3.5rem clamp(2rem, 5vw, 6rem) 3.5rem 0;

	border-right: 1px solid var(--border);
}

.hero-number {
	position: absolute;
	top: 2rem;
	left: 0;

	color: var(--text-muted);

	font-size: 0.65rem;
	font-weight: 650;
	letter-spacing: 0.1em;
}

.hero-copy {
	max-width: 780px;
}

.eyebrow {
	margin: 0 0 1.2rem;

	color: var(--text-muted);

	font-size: 0.65rem;
	font-weight: 650;

	letter-spacing: 0.13em;
}

.hero h1 {
	margin: 0;

	font-size: clamp(4rem, 6.8vw, 7.5rem);
	font-weight: 700;

	line-height: 0.9;
	letter-spacing: -0.065em;
}

.hero h1 span {
	display: block;
	color: var(--accent);
}

.intro {
	max-width: 480px;

	margin: 1.8rem 0 0;

	color: var(--text-secondary);

	font-size: 1rem;
	line-height: 1.65;
}

/* ================================
   ACTIONS
================================ */

.actions {
	display: flex;
	align-items: center;
	gap: 1.5rem;

	margin-top: 2rem;
}

.primary-action {
	display: inline-flex;
	align-items: center;
	gap: 0.8rem;

	padding: 0.85rem 1rem;

	border: 1px solid var(--text);

	background: var(--text);
	color: var(--text-inverse);

	font: inherit;

	font-size: 0.68rem;
	font-weight: 650;

	letter-spacing: 0.08em;
	text-transform: uppercase;

	cursor: pointer;

	transition:
		background 180ms ease,
		border-color 180ms ease;
}

.primary-action:hover {
	background: var(--accent);
	border-color: var(--accent);
}

.text-action {
	display: inline-flex;
	align-items: center;
	gap: 0.45rem;

	padding: 0;

	border: 0;

	background: transparent;
	color: var(--text-secondary);

	font: inherit;

	font-size: 0.7rem;
	font-weight: 600;

	cursor: pointer;
}

.text-action:hover {
	color: var(--text);
}

/* ================================
   RIGHT PANEL
================================ */

.hero-right {
	display: flex;
	align-items: center;

	padding: 2rem clamp(1.5rem, 4vw, 4rem);
}

.system-panel {
	width: 100%;

	border: 1px solid var(--border-strong);

	background: var(--bg-secondary);
}

/* panel top */

.panel-top {
	display: flex;
	align-items: center;
	justify-content: space-between;

	padding: 0.85rem 1rem;

	border-bottom: 1px solid var(--border);

	color: var(--text-muted);

	font-size: 0.58rem;
	font-weight: 650;
	letter-spacing: 0.1em;
}

/* panel main */

.panel-main {
	display: grid;
	grid-template-columns: 70px 1fr;
	gap: 1.5rem;

	padding: 2rem 1.5rem;

	border-bottom: 1px solid var(--border);
}

.panel-icon {
	width: 58px;
	height: 58px;

	display: flex;
	align-items: center;
	justify-content: center;

	border: 1px solid var(--border);

	color: var(--accent);

	background: var(--bg);
}

.panel-label {
	display: block;

	margin-bottom: 0.7rem;

	color: var(--text-muted);

	font-size: 0.58rem;
	font-weight: 650;
	letter-spacing: 0.1em;
}

.panel-main h2 {
	margin: 0;

	font-size: clamp(1.7rem, 2.5vw, 2.6rem);
	font-weight: 650;

	line-height: 1;
	letter-spacing: -0.045em;
}

.panel-main h2 strong {
	display: block;
	color: var(--accent);
	font-weight: inherit;
}

/* panel list */

.panel-list > div {
	display: grid;
	grid-template-columns: 35px 1fr;

	align-items: center;

	min-height: 48px;

	padding: 0 1.5rem;

	border-bottom: 1px solid var(--border);
}

.panel-list span {
	color: var(--text-muted);

	font-size: 0.58rem;
	font-weight: 650;
}

.panel-list p {
	margin: 0;

	font-size: 0.82rem;
	font-weight: 550;
}

/* panel bottom */

.panel-bottom {
	display: flex;
	justify-content: space-between;

	padding: 0.85rem 1rem;

	color: var(--text-muted);

	font-size: 0.55rem;
	font-weight: 650;

	letter-spacing: 0.1em;
}

/* ================================
   SERVICES
================================ */

.services {
	display: grid;
	grid-template-columns: repeat(3, 1fr);

	border-top: 1px solid var(--border);
	border-left: 1px solid var(--border);
}

.services button {
	display: grid;
	grid-template-columns: 28px 1fr 18px;

	align-items: center;
	gap: 0.8rem;

	min-height: 70px;

	padding: 0.75rem 1rem;

	border: 0;
	border-right: 1px solid var(--border);
	border-bottom: 1px solid var(--border);

	background: var(--bg);

	color: var(--text);

	text-align: left;

	cursor: pointer;

	transition:
		background 180ms ease,
		color 180ms ease;
}

.services button:hover {
	background: var(--bg-dark);
	color: var(--text-inverse);
}

.service-icon {
	color: var(--accent);
}

.service-content {
	display: flex;
	flex-direction: column;
	gap: 0.15rem;
}

.service-content small {
	color: var(--text-muted);

	font-size: 0.55rem;
	font-weight: 650;
}

.service-content span {
	font-size: 0.85rem;
	font-weight: 600;
}

.services button > svg {
	color: var(--text-muted);
}

.services button:hover > svg {
	color: var(--accent);
}

/* ================================
   BOTTOM LINE
================================ */

.bottom-line {
	display: grid;
	grid-template-columns: 1fr 1fr 1fr;

	align-items: center;

	padding: 0.75rem 0;

	color: var(--text-muted);

	font-size: 0.55rem;
	font-weight: 650;

	letter-spacing: 0.11em;
}

.bottom-line > span:nth-child(2) {
	text-align: center;
}

.bottom-line > span:last-child {
	text-align: right;
}

.bottom-line button {
	display: inline-flex;
	align-items: center;
	gap: 0.4rem;

	width: fit-content;

	padding: 0;

	border: 0;

	background: transparent;
	color: var(--text-secondary);

	font: inherit;
	font-size: inherit;

	letter-spacing: inherit;

	cursor: pointer;
}

.bottom-line button svg {
	color: var(--accent);
}

.bottom-line button:hover {
	color: var(--text);
}

/* ================================
   TABLET
================================ */

@media (max-width: 900px) {
	.hero {
		grid-template-columns: 1fr;
	}

	.hero-left {
		padding: 3.5rem 0 3rem;

		border-right: 0;
		border-bottom: 1px solid var(--border);
	}

	.hero-number {
		top: 1.5rem;
	}

	.hero-right {
		padding: 2rem 0;
	}

	.system-panel {
		max-width: 650px;
	}
}

/* ================================
   MOBILE
================================ */

@media (max-width: 600px) {
	.topbar {
		height: calc(var(--header-height) + 1rem);

		align-items: flex-end;
	}

	.location {
		display: none;
	}

	.brand-line {
		font-size: 0.6rem;
	}

	.hero-left {
		padding: 3rem 0 2.5rem;
	}

	.hero-number {
		top: 1.2rem;
	}

	.eyebrow {
		font-size: 0.6rem;
	}

	.hero h1 {
		font-size: clamp(3.3rem, 15vw, 5rem);
	}

	.intro {
		margin-top: 1.5rem;
		font-size: 0.95rem;
	}

	.actions {
		flex-direction: column;
		align-items: stretch;
		gap: 1rem;
	}

	.primary-action {
		width: 100%;
		justify-content: space-between;
	}

	.text-action {
		width: fit-content;
	}

	.hero-right {
		padding: 1.5rem 0;
	}

	.panel-main {
		grid-template-columns: 50px 1fr;
		gap: 1rem;

		padding: 1.5rem 1rem;
	}

	.panel-icon {
		width: 44px;
		height: 44px;
	}

	.panel-icon svg {
		width: 28px;
	}

	.panel-main h2 {
		font-size: 1.65rem;
	}

	.panel-list > div {
		min-height: 45px;
		padding: 0 1rem;
	}

	.services {
		grid-template-columns: 1fr;
	}

	.services button {
		min-height: 66px;
	}

	.bottom-line {
		grid-template-columns: 1fr;
		gap: 0.6rem;
	}

	.bottom-line > span {
		display: none;
	}
}
</style>
