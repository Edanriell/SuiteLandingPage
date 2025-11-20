<script lang="ts" setup>
	interface TextProps {
		classes?: string;
	}

	const { classes = "" } = defineProps<TextProps>();
</script>

<template>
	<p
		:class="[
			'font-[Epilogue] font-normal text-[18rem] leading-[160%] tracking-[0.01em] text-[var(--colors-neutral-500)] mb-[40rem] tablet:mb-[48rem] tablet:pr-[120rem] desktop:mb-[64rem] desktop:pr-[260rem]',
			classes
		]"
	>
		<slot />
	</p>
</template>
