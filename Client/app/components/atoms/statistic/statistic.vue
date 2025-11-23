<script lang="ts" setup>
	interface StatisticProps {
		label: string;
		value: string | number;
	}

	const { label, value } = defineProps<StatisticProps>();
</script>

<template>
	<div class="flex flex-col-reverse gap-y-[4rem] items-center tablet:basis-[192rem]">
		<dt
			class="font-[Epilogue] font-normal text-[16rem] leading-[150%] tracking-[0.16em] uppercase text-[var(--colors-neutral-500)]"
		>
			{{ label }}
		</dt>
		<dd
			class="font-[Epilogue] font-bold text-[48rem] leading-[120%] tracking-[-0.01em] uppercase text-[var(--colors-neutral-900)]"
		>
			{{ value }}
		</dd>
	</div>
</template>
