<script setup>
import { ArrowDownRight, ArrowUpRight, Boxes, GraduationCap, Headphones } from 'lucide-vue-next';
defineEmits(['go-to']);
</script>
<template>
	<section id="home" class="home">
		<div class="home-container">
			<div class="hero">
				<div class="hero-left">
					<span class="hero-number">00</span>
					<div class="hero-copy">
						<p class="eyebrow">BUSINESS TECHNOLOGY CONSULTANCY</p>
						<h1>
							Make your
							<span>business work</span>
							better.
						</h1>
						<p class="intro">The right software, systems and people to help your business work smarter and grow with confidence.</p>
						<div class="actions">
							<button type="button" class="primary-action" @click="$emit('go-to', 'solutions')">
								<span>Explore solutions</span>
								<ArrowUpRight :size="17" />
							</button>
							<button type="button" class="text-action" @click="$emit('go-to', 'about')">
								<span>About Softbox</span>
								<ArrowDownRight :size="16" />
							</button>
						</div>
					</div>
				</div>
				<div class="hero-right">
					<div class="system-panel">
						<div class="panel-top">
							<span>SOFTBOX / 00</span>
							<span>BUSINESS SYSTEMS</span>
						</div>
						<div class="panel-main">
							<div class="panel-icon">
								<Boxes :size="34" :stroke-width="1.2" />
							</div>
							<div>
								<span class="panel-label">WHAT WE DO</span>
								<h2>
									Technology that
									<strong>fits your business.</strong>
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
			<div class="services">
				<button type="button" @click="$emit('go-to', 'solutions')">
					<div class="service-icon">
						<Boxes :size="18" :stroke-width="1.4" />
					</div>
					<div class="service-content">
						<small>01</small>
						<span>Business Solutions</span>
					</div>
					<ArrowUpRight :size="15" />
				</button>
				<button type="button" @click="$emit('go-to', 'services')">
					<div class="service-icon">
						<GraduationCap :size="18" :stroke-width="1.4" />
					</div>
					<div class="service-content">
						<small>02</small>
						<span>Training & Mentorship</span>
					</div>
					<ArrowUpRight :size="15" />
				</button>
				<button type="button" @click="$emit('go-to', 'services')">
					<div class="service-icon">
						<Headphones :size="18" :stroke-width="1.4" />
					</div>
					<div class="service-content">
						<small>03</small>
						<span>Support & Maintenance</span>
					</div>
					<ArrowUpRight :size="15" />
				</button>
			</div>
			<div class="bottom-line">
				<button type="button" @click="$emit('go-to', 'about')">
					<span>SCROLL TO DISCOVER</span>
					<ArrowDownRight :size="14" />
				</button>
				<span>PORT HARCOURT · NIGERIA</span>
				<span>© SOFTBOX</span>
			</div>
		</div>
	</section>
</template>

<style scoped>
.home {
	min-height: 100svh;
	padding-top: var(--header-height);
	background: var(--bg);
	color: var(--text);
	border-bottom: 1px solid var(--border);
}

.home-container {
	width: 100%;
	max-width: var(--container);
	min-height: calc(100svh - var(--header-height));
	margin: 0 auto;
	padding-inline: var(--page-padding);
	display: flex;
	flex-direction: column;
}

.hero {
	flex: 1;
	display: grid;
	grid-template-columns: 1.15fr 0.85fr;
	min-height: 0;
}

.hero-left {
	position: relative;
	display: flex;
	align-items: center;
	padding: 2.5rem 3.5rem 2.5rem 0;
	border-right: 1px solid var(--border);
}

.hero-number {
	position: absolute;
	top: 1.25rem;
	left: 0;
	color: var(--text-muted);
	font-size: 0.62rem;
	font-weight: 650;
	letter-spacing: 0.1em;
}

.hero-copy {
	width: 100%;
	max-width: 680px;
}

.eyebrow {
	margin: 0 0 0.9rem;
	color: var(--text-muted);
	font-size: 0.62rem;
	font-weight: 650;
	line-height: 1.4;
	letter-spacing: 0.13em;
}

.hero h1 {
	margin: 0;
	color: var(--text);
	font-size: clamp(3.6rem, 5.8vw, 6.2rem);
	font-weight: 700;
	line-height: 0.92;
	letter-spacing: -0.065em;
}

.hero h1 span {
	display: block;
	color: var(--accent);
}

.intro {
	max-width: 440px;
	margin: 1.4rem 0 0;
	color: var(--text-secondary);
	font-size: 0.92rem;
	line-height: 1.6;
}

.actions {
	display: flex;
	align-items: center;
	gap: 1.25rem;
	margin-top: 1.6rem;
}

.primary-action {
	display: inline-flex;
	align-items: center;
	justify-content: center;
	gap: 0.7rem;
	padding: 0.72rem 0.9rem;
	border: 1px solid var(--accent);
	border-radius: var(--radius);
	background: var(--accent);
	color: var(--text-inverse);
	font: inherit;
	font-size: 0.64rem;
	font-weight: 650;
	line-height: 1;
	letter-spacing: 0.08em;
	text-transform: uppercase;
	cursor: pointer;
	transition:
		background 180ms ease,
		border-color 180ms ease,
		transform 180ms ease;
}

.primary-action:hover {
	background: var(--accent-hover);
	border-color: var(--accent-hover);
	transform: translateY(-1px);
}

.primary-action svg {
	flex-shrink: 0;
}

.text-action {
	display: inline-flex;
	align-items: center;
	gap: 0.4rem;
	padding: 0;
	border: 0;
	background: transparent;
	color: var(--text-secondary);
	font: inherit;
	font-size: 0.67rem;
	font-weight: 600;
	line-height: 1;
	cursor: pointer;
	transition: color 180ms ease;
}

.text-action:hover {
	color: var(--text);
}

.hero-right {
	display: flex;
	align-items: center;
	padding: 2rem 0 2rem 2.5rem;
}

.system-panel {
	width: 100%;
	border: 1px solid var(--border-strong);
	background: var(--bg-secondary);
}

.panel-top {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding: 0.7rem 0.9rem;
	border-bottom: 1px solid var(--border);
	color: var(--text-muted);
	font-size: 0.54rem;
	font-weight: 650;
	line-height: 1;
	letter-spacing: 0.1em;
}

.panel-main {
	display: grid;
	grid-template-columns: 52px minmax(0, 1fr);
	gap: 1.1rem;
	padding: 1.5rem 1.25rem;
	border-bottom: 1px solid var(--border);
}

.panel-icon {
	width: 50px;
	height: 50px;
	display: flex;
	align-items: center;
	justify-content: center;
	border: 1px solid var(--border);
	background: var(--bg);
	color: var(--accent);
}

.panel-label {
	display: block;
	margin-bottom: 0.5rem;
	color: var(--text-muted);
	font-size: 0.54rem;
	font-weight: 650;
	line-height: 1;
	letter-spacing: 0.1em;
}

.panel-main h2 {
	margin: 0;
	color: var(--text);
	font-size: clamp(1.45rem, 2.2vw, 2.2rem);
	font-weight: 650;
	line-height: 1.02;
	letter-spacing: -0.045em;
}

.panel-main h2 strong {
	display: block;
	color: var(--accent);
	font-weight: inherit;
}

.panel-list > div {
	display: grid;
	grid-template-columns: 30px minmax(0, 1fr);
	align-items: center;
	min-height: 42px;
	padding: 0 1.25rem;
	border-bottom: 1px solid var(--border);
}

.panel-list span {
	color: var(--text-muted);
	font-size: 0.54rem;
	font-weight: 650;
}

.panel-list p {
	margin: 0;
	color: var(--text);
	font-size: 0.75rem;
	font-weight: 550;
	line-height: 1.4;
}

.panel-bottom {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding: 0.7rem 0.9rem;
	color: var(--text-muted);
	font-size: 0.5rem;
	font-weight: 650;
	line-height: 1;
	letter-spacing: 0.1em;
}

.services {
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	border-top: 1px solid var(--border);
	border-left: 1px solid var(--border);
}

.services button {
	display: grid;
	grid-template-columns: 26px minmax(0, 1fr) 16px;
	align-items: center;
	gap: 0.7rem;
	min-height: 60px;
	padding: 0.6rem 0.8rem;
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
}

.service-icon {
	display: flex;
	align-items: center;
	justify-content: center;
	color: var(--accent);
}

.service-content {
	min-width: 0;
	display: flex;
	flex-direction: column;
	gap: 0.1rem;
}

.service-content small {
	color: var(--text-muted);
	font-size: 0.5rem;
	font-weight: 650;
	line-height: 1;
}

.service-content span {
	overflow: hidden;
	color: var(--text);
	font-size: 0.76rem;
	font-weight: 600;
	line-height: 1.3;
	text-overflow: ellipsis;
	white-space: nowrap;
}

.services button > svg {
	color: var(--text-muted);
	transition:
		color 180ms ease,
		transform 180ms ease;
}

.services button:hover > svg {
	color: var(--accent);
	transform: translate(2px, -2px);
}

.bottom-line {
	display: grid;
	grid-template-columns: 1fr 1fr 1fr;
	align-items: center;
	padding: 0.6rem 0;
	color: var(--text-muted);
	font-size: 0.52rem;
	font-weight: 650;
	line-height: 1;
	letter-spacing: 0.1em;
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
	gap: 0.35rem;
	width: fit-content;
	padding: 0;
	border: 0;
	background: transparent;
	color: var(--text-secondary);
	font: inherit;
	font-size: inherit;
	font-weight: inherit;
	line-height: 1;
	letter-spacing: inherit;
	cursor: pointer;
	transition: color 180ms ease;
}

.bottom-line button svg {
	color: var(--accent);
}

.bottom-line button:hover {
	color: var(--text);
}

@media (max-width: 900px) {
	.hero {
		grid-template-columns: 1fr;
	}

	.hero-left {
		padding: 3rem 0 2.75rem;
		border-right: 0;
		border-bottom: 1px solid var(--border);
	}

	.hero-right {
		padding: 1.75rem 0;
	}

	.system-panel {
		max-width: 650px;
	}
}

@media (max-width: 600px) {
	.home-container {
		padding-inline: var(--page-padding);
	}

	.hero-left {
		padding: 2.5rem 0 2.25rem;
	}

	.hero-number {
		top: 1rem;
	}

	.eyebrow {
		font-size: 0.57rem;
	}

	.hero h1 {
		font-size: clamp(3.1rem, 15vw, 4.8rem);
	}

	.intro {
		margin-top: 1.25rem;
		font-size: 0.88rem;
	}

	.actions {
		flex-direction: column;
		align-items: stretch;
		gap: 0.85rem;
	}

	.primary-action {
		width: 100%;
		justify-content: space-between;
	}

	.text-action {
		width: fit-content;
	}

	.hero-right {
		padding: 1.25rem 0;
	}

	.panel-main {
		grid-template-columns: 44px minmax(0, 1fr);
		gap: 0.9rem;
		padding: 1.25rem 1rem;
	}

	.panel-icon {
		width: 42px;
		height: 42px;
	}

	.panel-icon svg {
		width: 26px;
		height: 26px;
	}

	.panel-main h2 {
		font-size: 1.5rem;
	}

	.panel-list > div {
		min-height: 40px;
		padding-inline: 1rem;
	}

	.services {
		grid-template-columns: 1fr;
	}

	.services button {
		min-height: 58px;
	}

	.bottom-line {
		grid-template-columns: 1fr;
		gap: 0.55rem;
	}

	.bottom-line > span {
		display: none;
	}
}

@media (max-width: 400px) {
	.hero h1 {
		font-size: 3rem;
	}

	.panel-main {
		grid-template-columns: 1fr;
	}

	.panel-icon {
		width: 40px;
		height: 40px;
	}

	.panel-main h2 {
		font-size: 1.4rem;
	}

	.panel-bottom {
		font-size: 0.46rem;
	}
}
</style>
