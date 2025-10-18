<script lang="ts" setup>
	import ButtonGhost from "./button-ghost.vue";
	import ButtonSolid from "./button-solid.vue";

	interface ButtonProps {
		type?: "button" | "submit" | "reset";
		variant?: "ghost" | "solid";
	}

	const { type = "button", variant = "solid" } = defineProps<ButtonProps>();
</script>

<template>
	<ButtonGhost v-if="variant === 'ghost'" :type="type">
		<slot />
	</ButtonGhost>
	<ButtonSolid v-else-if="variant === 'solid'" :type="type">
		<slot />
	</ButtonSolid>
</template>
