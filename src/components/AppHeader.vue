<script setup>
defineProps({
	menuOpen: {
		type: Boolean,
		default: false,
	},
});

const emit = defineEmits(['toggle-menu', 'go-to']);
</script>

<template>
	<header class="header">
		<!-- Brand -->
		<button class="brand" type="button" aria-label="Go to home" @click="emit('go-to', 'home')">
			<img class="brand-logo" src="@/assets/images/icon.png" alt="Softbox Infotech Solutions Ltd" />

			<span class="brand-name"> SOFTBOX </span>
		</button>

		<!-- Menu -->
		<button class="menu-trigger" type="button" :class="{ open: menuOpen }" :aria-expanded="menuOpen" aria-label="Toggle navigation menu" @click="emit('toggle-menu')">
			<span class="menu-text">
				{{ menuOpen ? 'Close' : 'Menu' }}
			</span>

			<span class="menu-icon" aria-hidden="true">
				<i></i>
				<i></i>
			</span>
		</button>
	</header>
</template>

<style scoped>
/* =========================================================
   HEADER
   ========================================================= */

.header {
	position: fixed;
	inset: 0 0 auto;
	z-index: 1000;

	display: flex;
	align-items: center;
	justify-content: space-between;

	width: 100%;
	height: var(--header-height);
	padding-inline: var(--page-padding);

	background: var(--bg-dark);
	border-bottom: 1px solid var(--border);

	pointer-events: none;
}

.brand,
.menu-trigger {
	pointer-events: auto;
}

/* =========================================================
   BRAND
   ========================================================= */

.brand {
	display: flex;
	align-items: center;
	gap: 0.7rem;

	padding: 0;
	border: 0;
	background: transparent;

	color: var(--text);

	cursor: pointer;
}

.brand-logo {
	width: 40px;
	height: 40px;
	object-fit: contain;

	transition: transform 0.25s ease;
}

.brand:hover .brand-logo {
	transform: translateY(-1px);
}

.brand-name {
	color: var(--text);

	font-size: 0.78rem;
	font-weight: 700;
	letter-spacing: 0.14em;

	transition: color 0.25s ease;
}

.brand:hover .brand-name {
	color: var(--accent-hover);
}

/* =========================================================
   MENU
   ========================================================= */

.menu-trigger {
	display: inline-flex;
	align-items: center;
	gap: 0.8rem;

	padding: 0;
	border: 0;
	background: transparent;

	color: var(--text);

	cursor: pointer;
}

.menu-trigger:hover {
	color: var(--accent-hover);
}

.menu-text {
	font-size: 0.68rem;
	font-weight: 500;
	letter-spacing: 0.12em;
	text-transform: uppercase;
}

/* =========================================================
   MENU ICON
   ========================================================= */

.menu-icon {
	position: relative;

	display: block;
	width: 20px;
	height: 14px;
}

.menu-icon i {
	position: absolute;
	left: 0;

	width: 100%;
	height: 1px;

	background: currentColor;

	transition:
		transform 0.35s var(--ease),
		top 0.35s var(--ease);
}

.menu-icon i:first-child {
	top: 3px;
}

.menu-icon i:last-child {
	top: 10px;
}

/* =========================================================
   OPEN STATE
   ========================================================= */

.menu-trigger.open {
	color: var(--accent);
}

.menu-trigger.open .menu-icon i:first-child {
	top: 6px;
	transform: rotate(45deg);
}

.menu-trigger.open .menu-icon i:last-child {
	top: 6px;
	transform: rotate(-45deg);
}

/* =========================================================
   MOBILE
   ========================================================= */

@media (max-width: 600px) {
	.brand-logo {
		width: 36px;
		height: 36px;
	}

	.brand-name {
		font-size: 0.7rem;
	}

	.menu-text {
		font-size: 0.62rem;
	}

	.menu-icon {
		width: 18px;
	}
}
</style>
