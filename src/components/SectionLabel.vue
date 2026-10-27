<script setup>
defineProps({
	number: {
		type: String,
		required: true,
	},

	title: {
		type: String,
		required: true,
	},

	accent: {
		type: String,
		default: 'blue',
	},
});
</script>

<template>
	<div class="section-label" :class="`accent-${accent}`">
		<span>§ {{ number }}</span>

		<p>{{ title }}</p>
	</div>
</template>

<style scoped>
.section-label {
	display: flex;
	flex-direction: column;
	gap: 0.6rem;
	font-size: 0.65rem;
	font-weight: 600;
	text-transform: uppercase;
	letter-spacing: 0.14em;
}

.section-label span {
	color: var(--accent);
}

.section-label p {
	margin: 0;
	color: var(--text-secondary);
}

/* Optional darker accent */
.section-label.accent-black span {
	color: var(--text);
}

/* Soft blue accent */
.section-label.accent-blue span {
	color: var(--accent);
}

/* Mobile */
@media (max-width: 600px) {
	.section-label {
		font-size: 0.6rem;
	}
}
</style>
