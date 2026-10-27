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
							<ArrowUpRight :size="20" :stroke-width="1.5" aria-hidden="true" />
						</button>
					</div>
				</nav>
				<!-- CONTACT -->
				<div class="menu-contact">
					<span class="location"> PORT HARCOURT · NIGERIA </span>
					<div class="phone-links">
						<a href="tel:08026754712"> 0802 675 4712 </a>
						<a href="tel:07031093053"> 0703 109 3053 </a>
					</div>
				</div>
			</div>
		</aside>
	</Transition>
</template>
<style scoped>
/* =========================================================
   MENU
   ========================================================= */
.menu {
	position: fixed;
	inset: 0;
	z-index: 900;
	width: 100%;
	height: 100vh;
	background: var(--bg);
	color: var(--text);
	overflow-y: auto;
}
/* =========================================================
   INNER
   ========================================================= */
.menu-inner {
	width: 100%;
	min-height: 100%;
	padding: calc(var(--header-height) + 0.75rem) var(--page-padding) 1rem;
}
/* =========================================================
   NAVIGATION
   ========================================================= */
.navigation {
	width: 100%;
	border-top: 1px solid var(--border);
}
.nav-row {
	display: grid;
	grid-template-columns: 3.5rem 1fr;
	align-items: center;
	min-height: 4.6rem;
	border-bottom: 1px solid var(--border);
}
.nav-number {
	color: var(--text-muted);
	font-size: 0.65rem;
	font-weight: 600;
	letter-spacing: 0.1em;
}
.nav-link {
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 100%;
	height: 100%;
	gap: 1rem;
	padding: 0;
	border: 0;
	background: transparent;
	color: var(--text);
	text-align: left;
	cursor: pointer;
	transition:
		color 0.25s ease,
		padding-left 0.25s ease;
}
.nav-label {
	font-size: clamp(1.65rem, 3vw, 2.5rem);
	font-weight: 500;
	line-height: 1;
	letter-spacing: -0.035em;
	text-transform: uppercase;
}
.nav-link svg {
	flex-shrink: 0;
	color: var(--text-muted);
	transition:
		color 0.25s ease,
		transform 0.25s ease;
}
.nav-link:hover {
	padding-left: 0.3rem;
	color: var(--accent);
}
.nav-link:hover svg {
	color: var(--accent);
	transform: translate(3px, -3px);
}
/* =========================================================
   CONTACT
   ========================================================= */
.menu-contact {
	display: flex;
	align-items: center;
	justify-content: space-between;
	gap: 1.5rem;
	padding-top: 1rem;
}
.location {
	color: var(--text-muted);
	font-size: 0.62rem;
	font-weight: 600;
	letter-spacing: 0.1em;
	text-transform: uppercase;
}
.phone-links {
	display: flex;
	align-items: center;
	gap: 1.25rem;
}
.phone-links a {
	color: var(--text-secondary);
	font-size: 0.78rem;
	font-weight: 500;
	text-decoration: none;
	white-space: nowrap;
	transition: color 0.2s ease;
}
.phone-links a:hover {
	color: var(--accent);
}
/* =========================================================
   TRANSITION
   ========================================================= */
.menu-enter-active,
.menu-leave-active {
	transition:
		opacity 0.3s ease,
		transform 0.3s var(--ease);
}
.menu-enter-from,
.menu-leave-to {
	opacity: 0;
	transform: translateY(-10px);
}
/* =========================================================
   MOBILE
   ========================================================= */
@media (max-width: 600px) {
	.menu-inner {
		padding-top: calc(var(--header-height) + 0.5rem);
	}
	.nav-row {
		grid-template-columns: 2.75rem 1fr;
		min-height: 4rem;
	}
	.nav-number {
		font-size: 0.6rem;
	}
	.nav-label {
		font-size: 1.65rem;
	}
	.nav-link svg {
		width: 18px;
		height: 18px;
	}
	.menu-contact {
		align-items: flex-start;
		flex-direction: column;
		gap: 0.65rem;
		padding-top: 0.9rem;
	}
	.phone-links {
		gap: 1rem;
	}
	.phone-links a {
		font-size: 0.72rem;
	}
}
</style>
