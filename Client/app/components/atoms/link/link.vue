<script lang="ts" setup>
	import LinkGhost from "./link-ghost.vue";
	import LinkSolid from "./link-solid.vue";

	interface ButtonProps {
		to: string;
		variant?: "ghost" | "solid";
	}

	const { to, variant = "solid" } = defineProps<ButtonProps>();
</script>

<template>
	<LinkGhost v-if="variant === 'ghost'" :to="to">
		<slot />
	</LinkGhost>
	<LinkSolid v-else-if="variant === 'solid'" :to="to">
		<slot />
	</LinkSolid>
</template>
