<script setup>
import { ArrowUpRight } from 'lucide-vue-next';
defineProps({
	open: {
		type: Boolean,
		default: false,
	},
});
const emit = defineEmits(['close', 'go-to']);
const sections = [
	{ number: '00', label: 'Home', id: 'home' },
	{ number: '01', label: 'About', id: 'about' },
	{ number: '02', label: 'Solutions', id: 'solutions' },
	{ number: '03', label: 'Services', id: 'services' },
	{ number: '04', label: 'Contact', id: 'contact' },
];
const goTo = (id) => {
	emit('go-to', id);
	emit('close');
};
</script>
<template>
	<Transition name="menu">
		<aside v-if="open" class="menu" aria-label="Main navigation">
			<div class="menu-grid"></div>
			<div class="menu-line menu-line-left"></div>
			<div class="menu-line menu-line-right"></div>
			<div class="menu-inner">
				<!-- NAVIGATION -->
				<nav class="navigation" aria-label="Site sections">
					<div v-for="section in sections" :key="section.id" class="nav-row">
						<span class="nav-number">
							{{ section.number }}
						</span>
						<button class="nav-link" type="button" @click="goTo(section.id)">
							<span class="nav-label">
								{{ section.label }}
							</span>
							<ArrowUpRight :size="22" :stroke-width="1.4" aria-hidden="true" />
						</button>
					</div>
				</nav>
				<!-- CONTACT -->
				<div class="menu-contact">
					<span class="footer-label"> PORT HARCOURT · NIGERIA </span>
					<a href="tel:08026754712"> 0802 675 4712 </a>
					<a href="tel:07031093053"> 0703 109 3053 </a>
				</div>
			</div>
		</aside>
	</Transition>
</template>
<style scoped>
/* =========================================
   MENU
========================================= */
.menu {
	position: fixed;
	inset: 0;
	z-index: 900;
	background: var(--bg);
	color: var(--text);
	overflow-y: auto;
}
/* =========================================
   TECHNICAL BACKGROUND
========================================= */
.menu-grid {
	position: absolute;
	inset: 0;
	pointer-events: none;
	background-image: linear-gradient(to right, rgba(17, 19, 24, 0.045) 1px, transparent 1px), linear-gradient(to bottom, rgba(17, 19, 24, 0.045) 1px, transparent 1px);
	background-size: 80px 80px;
}
.menu-line {
	position: absolute;
	top: 0;
	bottom: 0;
	width: 1px;
	background: var(--border);
	pointer-events: none;
}
.menu-line-left {
	left: var(--page-padding);
}
.menu-line-right {
	right: var(--page-padding);
}
/* =========================================
   INNER
========================================= */
.menu-inner {
	min-height: 100vh;
	padding: calc(var(--header-height) + 1rem) var(--page-padding) 2.5rem;
	display: flex;
	flex-direction: column;
}
.navigation {
	margin-top: 0;
}
.nav-row {
	display: grid;
	grid-template-columns: clamp(4rem, 8vw, 7rem) 1fr;
	align-items: center;
	border-top: 1px solid var(--border);
	min-height: clamp(5.5rem, 9vw, 7.5rem);
}
.nav-row:last-child {
	border-bottom: 1px solid var(--border);
}
.nav-number {
	padding-left: clamp(1rem, 2vw, 2rem);
	color: var(--text-muted);
	font-size: 0.75rem;
	font-weight: 600;
	letter-spacing: 0.08em;
}
.nav-link {
	width: 100%;
	display: flex;
	align-items: center;
	justify-content: space-between;
	gap: 1rem;
	padding: 1rem 0;
	border: 0;
	background: transparent;
	color: var(--text);
	text-align: left;
	cursor: pointer;
	transition:
		color 180ms ease,
		padding-left 180ms ease;
}
.nav-label {
	font-size: clamp(2.4rem, 5vw, 4.8rem);
	font-weight: 650;
	line-height: 0.95;
	letter-spacing: -0.045em;
	text-transform: uppercase;
}
.nav-link svg {
	flex-shrink: 0;
	color: var(--accent);
	transition: transform 180ms ease;
}
.nav-link:hover {
	color: var(--accent);
	padding-left: 0.4rem;
}
.nav-link:hover svg {
	transform: translate(3px, -3px);
}
/* ─────────────────────────────────────────
   CONTACT
───────────────────────────────────────── */
.menu-contact {
	margin-top: clamp(2rem, 4vw, 3rem);
	padding: 1.5rem;
	border-top: 1px solid var(--border);
	display: flex;
	align-items: baseline;
	gap: 2rem;
}
.menu-contact .footer-label {
	margin-right: auto;
	color: var(--text-muted);
	font-size: 0.72rem;
	font-weight: 600;
	letter-spacing: 0.1em;
}
.menu-contact a {
	color: var(--text);
	font-size: 1rem;
	font-weight: 500;
	text-decoration: none;
	white-space: nowrap;
	transition: color 180ms ease;
}
.menu-contact a:hover {
	color: var(--accent);
}
/* =========================================
   HEADER
========================================= */
.menu-header {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding-bottom: 1.25rem;
	border-bottom: 1px solid var(--border);
}
.menu-meta {
	display: flex;
	align-items: center;
	gap: 1.5rem;
	color: var(--text-muted);
	font-size: 0.7rem;
	font-weight: 600;
	letter-spacing: 0.12em;
	text-transform: uppercase;
}
.menu-meta span:first-child {
	color: var(--accent);
}
.menu-index {
	color: var(--text-muted);
	font-size: 0.68rem;
	font-weight: 600;
	letter-spacing: 0.1em;
}
/* =========================================
   TRANSITION
========================================= */
.menu-enter-active,
.menu-leave-active {
	transition:
		opacity 0.4s ease,
		transform 0.4s var(--ease);
}
.menu-enter-from,
.menu-leave-to {
	opacity: 0;
	transform: translateY(-20px);
}
/* =========================================
   MOBILE
========================================= */
@media (max-width: 650px) {
	.nav-row {
		grid-template-columns: 3.2rem 1fr;
		min-height: 5.25rem;
	}
	.nav-number {
		padding-left: 0.5rem;
		font-size: 0.68rem;
	}
	.nav-label {
		font-size: clamp(2rem, 9vw, 3rem);
	}
	.nav-link svg {
		width: 20px;
		height: 20px;
	}
	.menu-contact {
		margin-top: 2.25rem;
		padding-top: 1.25rem;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 0.75rem 1rem;
	}
	.menu-contact .footer-label {
		grid-column: 1 / -1;
		margin-right: 0;
	}
	.menu-contact a {
		font-size: 0.9rem;
	}
}
</style>
