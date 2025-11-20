<script lang="ts" setup>
	interface SecondaryHeadingProps {
		before?: string;
		bold?: string;
		classes?: string;
		tag?: string;
	}

	const {
		before = "",
		bold = "",
		classes = "",
		tag = "h2"
	} = defineProps<SecondaryHeadingProps>();
</script>

<template>
	<component
		:is="tag"
		:class="[
			'font-[Epilogue] font-normal text-[48rem] leading-[120%] tracking-[-0.01em] text-[var(--colors-neutral-0)] text-center mb-[32rem] desktop:text-left',
			classes
		]"
	>
		{{ before }}
		<strong class="font-bold">{{ bold }}</strong>
	</component>
</template>
