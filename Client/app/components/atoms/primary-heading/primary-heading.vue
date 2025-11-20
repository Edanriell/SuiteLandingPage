<script lang="ts" setup>
	interface PrimaryHeadingProps {
		before?: string;
		highlight?: string;
		underlined?: string;
		middle?: string;
		afterBold?: string;
		classes?: string;
	}

	const {
		before = "",
		highlight = "",
		underlined = "",
		middle = "",
		afterBold = "",
		classes = ""
	} = defineProps<PrimaryHeadingProps>();
</script>

<template>
	<h1
		:class="[
			'font-[Epilogue] font-normal text-[38rem] leading-[110%] tracking-[-0.01em] text-[var(--colors-neutral-900)] mb-[24rem] tablet:text-[56rem] tablet:mb-[40rem] tablet:mt-[87rem] desktop:text-[72rem] desktop:mt-[98rem] desktop:mb-[40rem]',
			classes
		]"
	>
		{{ before }}
		<strong class="font-bold!">
			{{ highlight }}
			<span class="relative">
				<svg
					class="absolute top-[-24rem] left-[16rem] tablet:hidden"
					fill="none"
					height="17"
					viewBox="0 0 129 17"
					width="129"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M0.460449 15.2221C0.460449 15.2221 61.9093 -16.7779 128.016 15.2221"
						stroke="#172339"
						stroke-width="2"
					/>
				</svg>
				<svg
					class="hidden absolute top-[-62rem] left-[72rem] tablet:block desktop:hidden"
					fill="none"
					height="34"
					viewBox="0 0 288 34"
					width="288"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M0.459717 32.9999C0.459717 32.9999 138.72 -39.0001 287.46 32.9999"
						stroke="#172339"
						stroke-width="2"
					/>
				</svg>
				<svg
					class="hidden absolute top-[-62rem] left-0 desktop:block"
					fill="none"
					height="34"
					viewBox="0 0 288 34"
					width="288"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M0.459717 32.9999C0.459717 32.9999 138.72 -39.0001 287.46 32.9999"
						stroke="#172339"
						stroke-width="2"
					/>
				</svg>
				{{ underlined }}
			</span>
		</strong>
		{{ middle }}
		<strong class="font-bold!">
			{{ afterBold }}
		</strong>
	</h1>
</template>
